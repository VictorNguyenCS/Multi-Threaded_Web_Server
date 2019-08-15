
Created By: Thomas Swenson, Victor Nguyen, Daniel Rockcastle

Compilation
--------------------------------------------------------------------------------
To compile/run this code
 1. navigate to the file containting the server.c file, and
 2. make the program with the make command.
 3. run the webserver executable with:
  ./web_server port path num_dispatcher num_workers dynamic_flag queue_length cache_size
 4. open another terminal on the same machine, and perfrom wget requests.

How the code works
--------------------------------------------------------------------------------
This code works by creating a request processing system using threads. A queue of
requests is created based on what commands come into the web server, then they
are dequeed and distributed to worker threads that can execute the request
taking advantage of concurency of the threads.


Caching mechanism
--------------------------------------------------------------------------------
The caching mechanism used within this code, was least freqeuently used removal.
LRU means that when the cache is full it looks for the least frequently used
item in the cache and removes it first. this was done by creating a list to hold
each of the cache entries, form a cache entry struct with a variable marking how many times each entries
has been used.

