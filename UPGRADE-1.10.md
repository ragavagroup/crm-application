UPGRADE FROM any to 1.10
========================

## app/config/config.yml
- Removed `doctrine.dbal.default.wrapped_connection` service. 
- Removed `session.handler.pdo` service. From now a declaration of this service is located in `OroPlatformBundle`. Remove this service from your `app/config/config.yml` to be sure that PDO session will work properly. If you need to override this service, you can keep it in your `app/config/config.yml`, but make sure that a default database connection is not used here. You can use `doctrine.dbal.session_connection.wrapped` service if sessions are stored in a main database.
