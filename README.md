# clickhouse-example

Running ClickHouse column based database as docker containers on Linux host. </br>

### ClickHouse docker installation with mount volumes:

Create mount volume in host machine : </br>
`mkdir $HOME/clickhouse/clickhouse_db` </br>

Install click house as docker container: </br>
`docker run -d --name clickhouse-server --ulimit nofile=262144:262144 --volume=$HOME/clickhouse/clickhouse_db:/var/lib/clickhouse yandex/clickhouse-server` </br>

Container exposes 8123 port for HTTP interface and 9000 port for native client. </br>

Test connection using : `curl http://localhost:8123` , this should return an "Ok" response. </br>

Incase the container is running without any errors and the port 8123 is not accessible use "--network=host" to map container port with the host port. </br>

Refer main.go for a sample golang clickhouse example.
