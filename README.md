# wordpress in docker with mailcatcher

## example usage

- `docker-machine create --driver virtualbox default`
- `docker-machine start default`
- `eval $(docker-machine env default)`
- `docker-compose up -d`
- `open http://$(docker-machine ip default):1080/` (mailcatcher)
- `open http://$(docker-machine ip default):8000/wp-admin/` (WordPress)

## stop

- `docker-compose stop`
- `docker-machine stop default`

## re-start

- `docker-machine start default`
- `eval $(docker-machine env default)`
- `docker-compose start`

## clean up

- `docker-compose down`
- `docker-machine rm default`

## backup database

- `docker exec -it dockerwordpressmailcatcher_db_1 sh -c 'exec mysqldump --add-drop-table -u wp_user -phogehoge wordpress 2>/dev/null' > initdb.d/wordpress.sql`

## License

MIT License
