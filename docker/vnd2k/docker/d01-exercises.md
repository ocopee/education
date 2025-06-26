version: "3.8"

services:
  supertokens:
    image: supertokens/supertokens-postgresql
    container_name: supertokens
    restart: unless-stopped
    ports:
      - "3567:3567"
    environment:
      POSTGRESQL_USER: ocopee
      POSTGRESQL_PASSWORD: password
      POSTGRESQL_DATABASE_NAME: supertokens
    volumes:
      - supertokens-data:/var/lib/postgresql/data

volumes:
  supertokens-data:
    name: supertokens-data