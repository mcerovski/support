# h2database-docker
build : docker-compose build
run : docker-compose up -d

connect : jdbc:h2:tcp://localhost:1521/default
