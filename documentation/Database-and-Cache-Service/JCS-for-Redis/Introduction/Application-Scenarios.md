## Application Scenario

## Game Industry Application
- The game industry chooses Redis as an important function realization component.

Scenario 1: redis is used as a storage database

In the process of the game, the requirements for performance and interaction are very high. In view of the operational performance bottleneck of the database, most of the data will be stored in Redis as a persistent database.

Scenario 2: Redis is used as cache to accelerate application access

In the functional scene of a game, there will be daily tasks, achievements, various points ranking, functional activities, etc. Redis has advantages in providing services for such needs.

## E-commerce industry application
- It will be widely used in the e-commerce industry, mostly in commodity display, recommendation and other modules

Scenario 1: Seckilling shopping

Redis is used to bear huge instantaneous reading and writing pressure in large promotional activities.

Scenario 2: Application scenarios such as commodity sales and inventory

Real-time recommendation of goods and real-time update of goods inventory can be supported by the powerful performance provided by Redis.

## Live video application
- ## Redis will be used for live video applications on items and relation

Scenario 1: Storage user data

The explosively grown user data, interactive data, items and the like can be stored by Redis, and high availability of services can be achieved by adopting hot standby.

Scenario 2: Interest list

There are many interest links in the live broadcast system, such as stars, game players and so on. Users can use sets to obtain this kind of interest link and view the interest information from different anchors.



## Internet finance
- When Redis is used in internet finance, it acts as the restrictive function for the basic behavior pattern of users.

Scenario 1: Finance products seckilling

When the hard-to-get finance products are offered for sale, the overall access pressure of the system was very high, and the general database is unable to bear such reading pressure at all. The Cloud Database Redis supports the persistent function and can be directly used as a database system.

Scenario 2: system’s restriction on the types of operations that users purchase finance products

Some restrictions on user’s operations
