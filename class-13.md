# The Past, Present, and Future of Local Storage for Web Applications

![pic](http://statig0.akamaized.net/bancodeimagens/cy/4j/jo/cy4jjon7jpg95iabop3sz1d6k.jpg)

### A BRIEF HISTORY OF LOCAL STORAGE HACKS BEFORE HTML5

> In the beginning, there was only Internet Explorer. Or at least, that’s 
what Microsoft wanted the world to think. To that end, as part of the First
Great Browser Wars, Microsoft invented a great many things and included them in their browser-to-end-all-browser-wars,
Internet Explorer. One of these things was called DHTML Behaviors, and one 
of these behaviors was called userData.
userData allows web pages to store up to 64 KB of data per domain, in a hierarchical XML-based structure.
(Trusted domains, such as intranet sites, can store 10 times that amount. And hey, 640 KB ought to be enough for anybody.)
IE does not present any form of permissions dialog, and there is no allowance for increasing the amount of storage available.

### USING HTML5 STORAGE
> HTML5 Storage is based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key. 
The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats. However,
the data is actually stored as a string. If you are storing and retrieving anything other than strings,
you will need to use functions like parseInt() or parseFloat() to coerce your retrieved data into the expected JavaScript datatype.

### TRACKING CHANGES TO THE HTML5 STORAGE AREA
> If you want to keep track programmatically of when the storage area changes, you can trap the storage event
 . The storage event is fired on the window object whenever setItem(), removeItem(), or clear() is called and 
actually changes something. For example, if you set an item to its
existing value or call clear() when there are no named keys
  , the storage event will not fire, because nothing actually changed in the storage area.
  
  
  #### STORAGEEVENT OBJECT
  > The storage event is not cancelable. From within the handle_storage callback function, there is no way to stop the change from occurring. 
  It’s simply a way for the browser to tell you, “hey, this just happened. There’s nothing you can do about it now; I just wanted to let you know.”
  
  ### COMPETING VISIONS
  > One vision is an acronym that you probably know already: SQL. In 2007, Google launched Gears, an open source cross-browser plugin which included an embedded database based on SQLite. This early prototype later influenced the creation of the Web SQL Database specification. Web SQL Database (formerly known as “WebDB”) provides a thin wrapper around a SQL database, allowing you to do things like this from JavaScript:

 ***actual working code in 4 browsers***

openDatabase('documents', '1.0', 'Local document storage', 5*1024*1024, function (db) {
  db.changeVersion('', '1.0', function (t) {
    t.executeSql('CREATE TABLE docids (id, name)');
  }, error);
});



***WEB SQL DATABASE SUPPORT***

+ IE (.)
+ FIREFOX (.)
+ SAFARTI (4.0+)
+ CHROM (4.0+)
+ OPERA (10.5+)
+ IPHONI (3.0+)
+ ANDROID (2.0+)


[READ MORE](http://diveinto.html5doctor.com/storage.html)




