Make linqpad work with redshift.

Sounds easy there is already a  [linqpad driver for postrgres SQL](https://github.com/fknx/linqpad-postgresql-driver) which wraps a C# driver for postrgres SQL which support redshift [ngpsql](https://blog.rthand.com/post/2016/09/19/linqpad-llblgenpro-and-npgsql.aspx).

But hold your horses, reshift support for ngpsql was added after the linqpad driver was last compiled, so we'll need to update it to avoid software rot.

To build linqpad-driver need to start by setting $env:LINQPAD_HOME before launch the sln file.

Update nuget packages to latest versions
Update gitignore to clean up generated goop.

Issues:

* How to run tests (need localhost DB)
* How to run in linqpad (no lpx generated?)
