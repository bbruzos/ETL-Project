# ETL-Project
ETL Project

Step 1: E**xtract: your original data sources and how the data was formatted (CSV, JSON, pgAdmin 4, etc)

The first thing we did was find our souces. We both were interested in Nasa data so we found and extracted our CSV files from Kaggle.
The first CSV we used was a CSV of all Nasa Astrounauts. The second CSV we used was a CSV of all space missions conducted since 1957 globally.
The purpose of using these 2 CSVs was to see how many missions conducted by NASA astronauts were successful. This could be useful for a research project done by students, or for a documentary on NASA. By conducting ETL on this data, it will be easier for our clients to see and analyze how many NASA space missions were successful.

Step 2: T**ransform: what data cleaning or transformation was required.

For these 2 CSVs, we had to transform the data multiple times. First, we worked on the Astronaut dataframe. We transformed this DataFrame and split the missions column. We created 4 columns for missions. We then did the same thing for the space missions DataFrame. These were crucial steps to transforming the DataFrames because we needed to make sure all missions were split. Furthermore, we had to split the astronaut DataFrame and remove the parentheses around some of the mission names. Without doing this, we would have not been able to join later on in the ETL process. One of the most important things we did  was use the melt function in pandas to stack all of the missions in their respective DataFrames. Once all the missions were in one column, we then removed all "None" and "NaN" values. The last step before merging the 2 DataFrames was to strip all the "Missions" columns in both DataFrames of any spaces before or after the characters. Once this was done, we were able to do an inner join on the Missions column from each DataFrame. This will allow our client to see that there are 597 NASA missions completed since 1957. This will allow our clients to also analyze the NASA missions that were successful and to see who were the astronauts that were involved in the mission. 

Step 3: L**oad: the final database, tables/collections, and why this was chosen.

This was loaded to the PostgreSQL database. We chose to use a relational database such as PostgreSQL because it provides data accuracy as well as easy access to data quickly. NASA is also one of the biggest companies that use MySQL to store their data. Because NASA datasets can be very large, using a relational database is beneficial because it can be a quick access and provides data integrity. 

This new DataFrame was loaded into the SQL database. We created an astronaut_missions table in PostgreSQL.

Overall, we were able to extract data, transform it in pandas and then load it into the PostgreSQL database. 
