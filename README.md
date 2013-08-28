Sneakerhead

A small groovy and grails applicaiton to manage my shoe collection. This is just a small app I decided to write to help me learn Groovy and Grails. Think of this as a community based website where users can show off their sneaker collection.

Here are some random features this applicaiton will have. 

Public 
 + Bootstrap UI
 + Home page will just be a list of users that have profiles in our system
 + View list of shoes for a particular user. Allow sorting paging and searching.
 + Switch to grid view to show thumbnails instead of list.
 + View details shows pictures and allows for comments. Use https://disqus.com
 + details page will have some social integration with facebook + twitter. 

Admin
 + Secure admin area to manage profile data + collection information
 + manage only data that belongs to this user

Future Features

- I think the 1st revision of this will only be for me but a future version can take a user profile approach where each
user can show off their collection. 
- REST API 
- The idea of following another user to have a facebook type wall on your home page listing new shoes added by friends.
- find users by location
- some kind of cool view that is just a wall of photos and you can click through to view details
- mogodb integration
- storing images somewhere else such as amazon s3

Please send any ideas you have for this little ficticious application to danvega at gmail dot com.


Setup
===================================================================================

I have my local instance running off of a mysql database. You can create a mysql database and change the datasource
settings for development to match your setup or you can easily go back to an in memory h2 database. 
1st in buildConfig.groovy you will want to comment out the following line. 

	runtime 'mysql:mysql-connector-java:5.1.22'

Next update the the datasource closure under development in DataSource.groovy to something like this

	dataSource {
	    dbCreate = "create-drop"
	    url = "jdbc:h2:mem:sneakerhead;MVCC=TRUE;LOCK_TIMEOUT=10000"
	}

