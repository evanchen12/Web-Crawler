# bgp_router
Evan Chen & Kevin Jen

# Approach --- 
For this project first send a GET request which the server will return a response. From the response we were able to obtain the csrf middleware token, csrf token and session id. With these tokens we can add them to our POST request along with our username and password. The response from the login request will give us the new session id and csrf token for our new cookie. Next_link is the link we are looking at. We have 2 arrays link_to_search and link_searched, which is self explainatory. Then we have our while loop to parse through the different response codes and sending GET request for response code. 

200 OK: Move next_link from link_to_search to link_searched. Look for flags. Gather all the links that isn't in link_to_search and link_searched and also is part of    fakebook into link to search. Finally, set the next_link to the first of link_to_search

302 Found: Move next_link from link_to_search to link_searched. Set the new location from the response as our next_link.
 
403 and 404: Move next_link from link_to_search to link_searched and move on.

503: Just continue the loop

# Challenges --- 
- We had trouble figuring out the POST function. We spend a good while figuring out what the format for it is.
- We were getting different results with the same code where Evan got 302 found and Kevin got 200 OK. We figured out that Kevin was entering the wrong username. 

# Design and features --- 
- We seperated the socket and send request into its own function  

# Testing --- 
For testing we use just run the program and judging from the outputs.
