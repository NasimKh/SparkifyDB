

<h4>Sparkify data modelling</h4>
<p>Sparkify is collecting data in json format. However they need a database to be able to run analytics reports on users and artists and songs played </p>


<h4> Fact Table </h4>
<p>The fact table consist of songplays. Values included in this table are as follow : </p>
    <blockquote> songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
    </blockquote>

<h4>Dimension Table</h4>
<p>The dimension tables include data about artist, song , time and user.
    Each table consist of the folowing : </p>

<blockquote> Artist information: artist_id, name, location, latitude, longitude </blockquote>

<blockquote> Song information  : song_id, title, artist_id, year, duration</blockquote>
<blockquote> timestmap of songs being played : start_time, hour, day, week, month, year, weekday</blockquote>
<blockquote> user that played the song  : user_id, first_name, last_name, gender, level</blockquote>

<h4>Why star Schema</h4>
Since quering the database and it being performant is the most important measure for spakify , The star schema is the best choice here.
<h4> query example</h4>
<blockquote> %sql SELECT * FROM songplays limit 10 ;
</blockquote>

<h4>Files</h4>

<p> <strong>Create_table.py</strong> is the code to create tables </p>
<p><strong> sql_queries.py </strong> creates the tables and contains the insert statments for database</p>
<p><strong>etl.py</strong>Creates the ETL pipeline. connects to database and writes json data into database </p>
<p><strong>etl.ipynb</strong> notebook of ETL . This file is not necessary to run the program</p>
<p><strong>test.ipynb</strong> Connects to Db and test if the data has been written correctly to DB</p>

<h4>How to run the code</h4>
On your terminal please run the following :
<blockquote>python create_table.py <br>
            python etl.py</blockquote>

<h4>Enviroment</h4>
Python 3.6.3 <br>
psql (PostgreSQL) 9.5.23 <br>
psycopg2==2.7.4


<h4>Sources</h4>
http://gkmc.utah.edu/ebis_class/2003s/Oracle/DMB26/A73318/schemas.htm <br>
https://www.dataquest.io/blog/loading-data-into-postgres/ <br>
https://gist.github.com/gwangjinkim/f13bf596fefa7db7d31c22efd1627c7a <br>
https://github.com/san089/Udacity-Data-Engineering-Projects/blob/master/Data_Modeling_with_Postgres/README.md <br>
