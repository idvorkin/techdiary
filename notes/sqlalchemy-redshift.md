SQLAlchemy Docs: 
   *  http://docs.sqlalchemy.org/en/latest/orm/tutorial.html

Install dependant package:

    pip install sqlalchemy-redshift

Install required certificates:

* https://docs.aws.amazon.com/redshift/latest/mgmt/connecting-ssl-support.html
* https://stackoverflow.com/questions/28228241/how-to-connect-to-a-remote-postgresql-database-with-python

Load sqlalchamey

    import sqlalchemy as sa
    username="idvorkin"
    connect_args={'sslmode':'verify-ca'} # see issues with cert remapping -sigh
    engine = sa.create_engine(f'redshift+psycopg2://{username}:{password}@{db}',connect_args=connect_args)

Reflect Tables

    # not sure why can't enumarete pg_catalog.
    # using psql can enumerate with \dn
    # https://dba.stackexchange.com/questions/40045/how-do-i-list-all-schemas-in-postgresql
    pg_catalog = sa.MetaData(schema="pg_catalog")
    pg_catalog.reflect(bind=engine)
    for table in pg_catalog.tables: print (table) 
