# create ElephantSQL instance

# use it with postico

# Sequelize (obj relational mapping library)

## set up

### $ npm init -y, $ git init, $ touch .gitignore (add node_modules to .gitignore)

### $ npm install sequelize sequelize-cli

### $ npm install pg

### To setup sequelize for use inside your project run: $ npx sequelize-cli init

### Let's make our inital commit at this stage, run: $ git add ., $ git commit -m 'Initial commit, sequelize init'

# Connecting to the database

## add this to your .json file

"development": {

"url": "postgres://sialuzfd:hVxgAW_Yvvk4O32dvzqjqIM7b1rjVEo3@balarama.db.elephantsql.com:5432/sialuzfd",

"dialect": "postgres"

},

### Let's test this first step! We need to see if Sequelize can connect to postgres. To check this we can run: $ npx sequelize-cli db:migrate

### One last thing we have to tweak in Sequelize's default configs is in models/index.js. Open that file up and check the line 15 where we have: (replace it with) sequelize = new Sequelize(config.url, config);

# define a user: $ npx sequelize-cli model:generate --name user --attributes name:string,email:string,phone:integer,password:string

### So, to actually create our users table let's run the related migration. To do so execute in your terminal the following command: $ npx sequelize-cli db:migrate

### Now that our table is set up we'll go into the next step, getting some data into our users table. And in come Seeds to help us do so. Seeding a database is a process in which an initial set of data is provided to a database. It's a nice way to populate our tables with data after we create them. To do so we must first generate the skeleton of a seed file using our CLI. Run: $ npx sequelize-cli seed:generate --name some-users

## Now we'll run the seed to make sure our table gets some data. To run do:

### $ npx sequelize-cli db:seed:all

### To un-do the seed we can use

### $ npx sequelize-cli db:seed:undo:all

### We can also point to a specific seed file to run instead of "all" using the --seed flag

### $ npx sequelize-cli db:seed --seed 20191211110453-some-users

### $ npx sequelize-cli db:seed:undo --seed 20191211110453-some-users.js (.js at the end of the file required to be able to run)
