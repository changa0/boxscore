README.md

# SlimScore
### v1.0.3

## View today's nba game scores

[Use application here](https://changa0.github.io/boxscores/)

[Chrome extension version](https://github.com/changa0/boxscoreschrome)

An application with a small footprint for viewing live NBA game scores, compatible with desktop and mobile web browsers

### Issues/Notes

* Full box score for in progress games and completed is now functional
* The proxy increases response times, particularly when Heroku dyno is in sleep. **When dyno is asleep, getting live game data may take around 5-10 seconds initially.**
* Scoreboard endpoint restricts heroku/aws/other web host access and thus must use JSONP. Only github.io is whitelisted to use the proxy
* Rarely, teams under team records are in upcoming games may differ from the ones selected, this is due to an issue with nba's stats api mixing up the order in the requested data
* Similarly, the names of teams shown for inactive games may differ from teams selected in dropdown menu, due to mixed up orders in the data returned by the api (LastMeeting order different from GameHeader)
* Google chrome version is available, uses cross origin XHR requests instead of jsonp, allowed by extension permissions. Supports live full box scores with player statistics, more responsive than github.io version since proxy is not needed, no proxy delay or sleep delays.
* iOS small screens, table overflow scrolling doesn't seem to work, scrolls entire page instead. Inconclusive cause, possibly because table is generated dynamically.
* 9/28/2020 - changed API endpoint for populating scores, old endpoint seemed server restricted
