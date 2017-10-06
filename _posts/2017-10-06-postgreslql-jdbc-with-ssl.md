# Setup Postgres JDBC with SSL
I had never setup postgres + jdbc + ssl before so I thought I would give it a shot today. The newer versions of postgres 9.6+ seem to have ssl configured out of the box. I did not find an easy answer in my googling of "How to setup postgres jdbc with ssl" so I thought I would quickly write it up. 

Basically all you have to do is modify your connection string to look like this: `postgres://user:password@host/dbname?ssl=true&sslfactory=org.postgresql.ssl.NonValidatingFactory`

Obviously you will want to setup properly signed certs in production so you will not need to use the NonValidatingFactory, but for testing this works just fine.

NOTE: I am using slick for all my database interactions and it accepts the url above for postgres connections if you are using another library it is possible the format may be different.
