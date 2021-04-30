[![Board Status](https://dev.azure.com/lvtetrault/0936d065-933d-4a39-8b15-0f8a4af1794b/bc5ec5c2-1368-44b2-a4fc-1415bb7bd116/_apis/work/boardbadge/3b6dbbc7-a4da-45f9-bed3-477aa020a032)](https://dev.azure.com/lvtetrault/0936d065-933d-4a39-8b15-0f8a4af1794b/_boards/board/t/bc5ec5c2-1368-44b2-a4fc-1415bb7bd116/Microsoft.RequirementCategory)
# fantasydata-api-node
[FantasyData](https://fantasydata.com) API client library wrapper for Node. For more information on the FantasyData API check the [Fantasy Data Developer Portal](https://developer.fantasydata.com/?developer-portal). There are no external dependencies for this package aside from [node](https://nodejs.org/).

## Installation
This library is distributed on `npm`. In order to add it as a dependency, run the following command:

``` sh
$ npm install --save fantasydata-node-client
```

## Authentication
You can find your api keys in the [Fantasy Data Developer Portal](https://developer.fantasydata.com/developer). See [Usage](#usage) for implementation details.

## Usage
In this simple example we authenticate two clients, `MLBv3Stats` and `MLBv3Projections`, with their respective keys. We then pull standings for `2018` and do whatever we need to with the JSON returned.
``` js
const fdClientModule = require('fantasydata-node-client');
const keys = {
    'MLBv3StatsClient':'YOUR-MLBV3STATS-KEY',
    'MLBv3ProjectionsClient':'YOUR-MLBV3PROJECTIONS-KEY'
};
const FantasyDataClient = new fdClientModule(keys);
    
FantasyDataClient.MLBv3StatsClient.getStandingsPromise('2018')
    .then((resp) => {
        // data here
    })
    .catch((err) => {
        // handle errors
    });
```

## Documentation
* [Fantasy Data Developer Portal](developer.fantasydata.com/?developer-portal)
* [Implementation Guide](https://fantasydata.com/resources/implementation-guide.aspx)
* [Data Dictionary](https://fantasydata.com/resources/data-dictionary.aspx)
