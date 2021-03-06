Thanks to CrookedNumber for the basecode and the idea of a [trello shell script](https://gist.github.com/CrookedNumber/8857003).  This repo is a "fork" of his gist that has better input sanitization and more features.

##install##
1. clone the repo into a folder already in your PATH environment variable, or add the folder you clone to to your path.
2. use https://trello.com/1/authorize?response_type=token&key=dde1edb7e72a3c12ed94e0fd6bbcba05&scope=read,write&expiration=1day&name=linuxTrello to get a day-long token (replace "1day" with "never" if you don't want to get a new token each day), then place it in trello.token in the same folder to get this to work.
3. Find the boards you would like to post to, and find the board IDs in their URLs. It'll be the ~8 character hash-like string in the URL. E.g., for https://trello.com/b/aWsGTrsD/work the ID is aWsGTrsD
4. One by one, plug those IDs (along with your token from above) into the following API call: https://trello.com/1/boards/{insertBOARDIDhere}/lists?key=dde1edb7e72a3c12ed94e0fd6bbcba05&token={YourTrelloToken} (via browser or cURL)
5. Look at the resulting json, and, for each board, decide on the list (e.g, doing, To Be Done, misc) where you would most likely put a quick placeholder card. Make note of the 'id' property for each chosen list (you can have multiple per board, just don't name the shorthand after the board if that is the case).
6. Take the list IDs from above and put each one with the desired shorthand into a case statement where I have my lists in the boilerplate version you cloned.

 
