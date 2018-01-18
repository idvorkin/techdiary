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

    meta = sa.MetaData()
    meta.reflect(bind=engine)
    or table in meta.tables: print (table) 
