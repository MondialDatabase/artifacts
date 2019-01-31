# Major Project

*This documents contents was retrieved on 2019-01-13 from [here](http://ksuweb.kennesaw.edu/~bsetzer/8990fa14/nanoc/output/projects/) for archival purposes.*
*Content not related to the project description has been removed for brevity.*

The graduate course will have one major project this term.
The project will deal with the Mondial database.
You will create a small web site that will display data from the database.

The first page will let the user choose a country.
Use a single-selection list for this purpose.
Populate the list from the database to accommodate any changes.

The first page will also let the user select which data about a country to display.
Use checkboxes for this.
The choices include the following information.

1. Some choices are about individual pieces of information
    * population
    * area
    * infant mortality
    * population growth rate
    * government
    * independence data
    * GDP: gross domestic product (in million $)
    * percentage of agriculture of the GDP
    * percentage of services of the GDP
    * percentage of industry of the GDP
    * inflation: inflation rate (per annum)
    * Type of government
    * Independent or not
        * If independent, give data of independence
        * If not independent, give name of country on which it is depndent
    * total length of the border of the country
    * capital of the country
2. Some choices result in lists
    * List the languages spoken in the country and the percentage of the
  population the speaks each language
    * List the religions observed in the country and the percentage of the
  population associated with each religion
    * List the ethnic groups in the country and the percentage of the population
  in each group.
    * List the countries bordering this country and the length of each border
    * List to which continents the country belongs
    * List the names of the cities in the country
    * List the mountains in the country
    * List the seas in the country
    * List the rivers in the country
    * List the islands in the country  
    * List the lakes in the country
    * List the deserts in the country

Once the user has made selections, a submit button will lead to a page that displays all of the
requested information (and only the requested information).

On the first page,
also provide an **ALL** button that will request all of the information for the selected country.

The mondial database will be available from a PostgreSQL server with the database name *mondial*,
the user *mondial* and the password *mondial*.

You can test your code by setting up the database yourself.
Check the [Mondial site](http://www.dbis.informatik.uni-goettingen.de/Mondial/)
for the files to set up the database in PostgreSQL.
Alternatively, the files are available in the extras folder:

* [mondial-schema-postgresql-2010.sql](http://cs.kennesaw.edu/~bsetzer/4320fa14/extra/databases/mondial-schema-postgresql-2010.sql)
  run this script first to set up the necessary tables
* [mondial-inputs-postgres-2010.sql](http://cs.kennesaw.edu/~bsetzer/4320fa14/extra/databases/mondial-inputs-postgresql-2010.sql)
  run this script second to insert the data


Use templates to generate the two pages, preferably the Jinja2 templating package discussed in class.
