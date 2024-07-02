back end sprint boot app 

the serever is:

http://localhost:8080



the mane endpont 
get all the employees:
GET /api/v1/employees

create employee 
POST /api/v1/employees

get employee by id 
GET /api/v1/employees/{id}

update employee 
PUT /api/v1/employees/{id}

delete employee 
Delete /api/v1/employees/{id}

to run the app use 

docker compose -f "docker-compose.yml" up  --build   
or 
docker-compose up --build


torun in the backrund us 
docker compose -f "docker-compose.yml" up -d  --build  



    Start Services with Build:

    bash

docker compose -f "docker-compose.yml" up --build

or

bash

docker-compose up --build

Start Services in Background with Build:

bash

docker compose -f "docker-compose.yml" up -d --build

or

bash

    docker-compose up -d --build

Checking Services

After starting the services, you can check their status and logs:

    List Running Services:

    bash

docker-compose ps

View Logs:

bash

docker-compose logs -f

Stop and Remove Services:

bash

docker-compose down