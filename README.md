# Full-Stack-VRP

  The Vehicle Routing Problem is a combinational optimization problem which the goal is to find optimal routes for multiple vehicles to visiting a sets of locations. It generalises the Traveling Sales Man problem.
  Different to the general VRP, where all vehicles come out from the same depot. We want to focusing on optimizing routes that going into the depot. 
  > Imaging you and your friends are going to the place for some event. Some of your friend has a car, and some does not. What is the optimim way to distribute for car pool such that every one will get to the event place with the mimimum of driving distance. 
  
Though the problem changed to multiple deports to a single destination, we could still apply the same algorithm for VRP in our problem. We used Inter/Intra local route search in our case.

- Backend:
    - We choose to use flask as our backend framework, and PosgreSQL as our database to store the user information. 
    - Usd Google Oauth API for user to login. We also generated our own JWT when retriving data from the database.
    - Inter/Intra local search algorithm for optimizing the routes.
    - Periodic timer for the route calculating and sending emails to the user. 
- Frontend:
    - Used Vue framwork

- Dockerized the whole package so that server could run on differnt operating system.
- Freed local machine byt Seting up a remote docker machine for deploying the web server remotely. 
      
## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Backend

##### Prerequisites

> You will need docker running on your local machine.

> Register for **Google developer consol** and get the Google API keys as environment variables for the project. 
Find the useful information [here](https://developers.google.com/).

    APIs needed to registart and obtain secret keys:

    Google Oauth, 
    Google Places, 
    Google Distance Matrix, 
    Google Geocoding, 
    Google Maps Static

> Have your web server and your own domain set up properly and obtain the access token and secrete key accordingly.

For writing the secrete keys into the environment variables, please refer to the **".env"** file for proper input format.


After pulled this project, go to the docker-compose.yml directory and type in the following command.

```
docker-compose build
docker-compose up -d db
docker-compose run --rm web /bin/bash -c "python -c  'import database; database.init_db()'"
docker-compose up
```
Only run those following commands
```
docker-compose run --rm web /bin/bash -c "python -c  'import database; database.init_db()'"
```
When you **first** build and run the project, this will initialized your database and bootstrap the datatable.
After the initialization, you could skip these two commands, and simply do "docker-compose up"


##### Running the tests *(only for routing calculating function)*

Refering to [test.py]([here](https://developers.google.com/).) under flaskr folder. 

Write out your own problem for testing your solver.

#
### Frontend
##### Project setup
```
npm install
```

##### Compiles and hot-reloads for development
```
npm run serve
```

##### Compiles and minifies for production
```
npm run build
```

##### Run your tests
```
npm run test
```

##### Lints and fixes files
```
npm run lint
```

##### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
#


## Authors

* **Tony Fei** - [GitHub page](https://github.com/sa-tony)
* **Kenan Lv** - [GitHub page](https://github.com/kenanlv)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* [Inter/Intra Local Search](https://github.com/topics/vehicle-routing-problem?l=python)

## Further Readings

* The Taxi-problem
* Dail-a-ride

# 
