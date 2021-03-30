# openbrewerydb-graphql

In order to add a Relational DB we need to manually create the RDS instance following the steps specified
in https://docs.amplify.aws/cli/graphql-transformer/relational

Once created, we need to create the breweries table, using the folllowing SQL:

```
Use breweries;

CREATE TABLE breweries (
id INT AUTO_INCREMENT, name varchar(255) not null, brewery_type varchar(100), street varchar(255), city varchar(100),
state varchar(100), postal_code varchar(20), website_url varchar(255), phone varchar(20), created_at timestamp default
NOW() NOT NULL, updated_at timestamp default NOW()  NOT NULL, country varchar(100), longitude decimal, latitude decimal,
address_2 varchar(100), address_3 varchar(100), county_province varchar(100), constraint breweries_pkey primary key (id)
);
```

After the RDS is created, we need to import it into Amplify with the following command:
`amplify api add-graphql-datasource`
