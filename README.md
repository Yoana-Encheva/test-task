# Task

We would like you to make a step-by-step code review of the code snippet in the link below and record a video in English. In this video, you should describe what do you need in order to run it, what is its purpose, the expected result, and external dependencies.

# Purpose

- The purpose of the code is to grab a CSV file with suffix technologies.csv, grab the predefined columns in the testData object, get the value for each column from each row and build an object with the column name being the object property key.

# Dependencies

In order to run the code I need to setup package.json so I define any depdencies I need and install them using a package manager.

- Running _npm init_ will ask me a bunch of questions about my package and create a package.json
- The code itself requires one external dependecy called _csv-parse_. Once I define package.json I can run _npm install csv-parse_ which will install the external dependency needed.

# Running the code

- The file itself exports the function getData but it won't execute it. In order for this function to be executed I will need to import the function from the executable file and execute it, e.g. index.js. The function receives as a parameter the prefix of the csv file which needs to be passed.

We can create an index.js file and type the following in order to run it:

```
 const getData = require("./parser");

 async function start() {
   const cards = await getData("version_");
   console.log('cards: ', cards);
 }

 start();
```

# Errors

There is one error in the code. The function _configFileLocation_ is not returning anything as the object has been defined after return. We need to open the object { after the return like the following:

```
  const configFileLocation = (name) => {
    return {
      filename: path.join(__dirname, `${name}technologies.csv`),
    };
  };
```

# Creating a file

When the program runs it will look for a cvs file which it can parse. I need to create a csv file in my root directory so it can use it to parse the data.
For my example I will create a file called versions*technologies.csv and pass the prefix of \*versions\*\* to the *getData\* function so it can find the file.

# Running the program

Run the following commands to execute the script:

npm install
npm start

You should see an output in the terminal, logging the details from the CSV file
