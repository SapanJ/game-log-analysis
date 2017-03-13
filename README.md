# game-log-analysis
Get sensible outcome from a huge log file of any game application 

# Calculate total number of Valid Sessions for a Game
1. Calculate the number of sessions (valid and total) of a game and the average session time(only valid) from the given dataset and explain your calculation strategy.
2. Provide insights about users (if any)
3. Point out discrepancies in the data and suggestive work around (if any)

# Insight about Available Data
1. A session typically starts with a GGSTART event
2. A session typically ends with a GGSTOP event.
3. If there is a time difference of more than 30 secs between a GGSTOP and GGSTART, they are considered to be different sessions.
4. There can be multiple GGSTART and GGSTOP calls in a single session.
5. If a session is more than 60 seconds long, it is classified as a valid session.
6. If a session is less than 1 second, it should be ignored
7. Incase of multiple GGSTART and GGSTOP calls, the exact time of the session should be taken for establishing session validity (not the difference between the first GGSTART and the last GGSTOP call)

# A brief description of some of the fields:
ai5 ->   Oneway hash of a particular device identifier sdkv Mobile SDK version event Type of event on the mobile device (GGSTART or GGSTOP)
game_id ->  Unique Identifier for a particular game timestamp Time when the request arrived on server (GMT)ts Epoch timestamp value of the device
