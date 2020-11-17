# Docker + Rails + Postgres

This is based on [the offical Docker docs workflow](https://docs.docker.com/compose/rails/), updated to support the early 2020 Docker-lib/Postgres [breaking changes](https://github.com/docker-library/postgres/issues/681).

```sh
docker-compose up
```

The app will be running at http://localhost:3000/

> If you make changes to the Gemfile or the Compose file to try out some different configurations, you need to rebuild. Some changes require only docker-compose up --build, but a full rebuild requires a re-run of docker-compose run web bundle install to sync changes in the Gemfile.lock to the host, followed by docker-compose up --build.

To run rails commands:

```sh
docker-compose run web rails generate controller home index
```

To create the DB (if needed):

```sh
docker-compose run web rake db:create
```

See [here](https://stackoverflow.com/a/31542717/1446845)
