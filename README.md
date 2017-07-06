## `exit_to=` to `destination=`

[![Continuous Integration](https://travis-ci.org/mapbox/rewrite-exit-destination-signage.svg?branch=master)](https://travis-ci.org/mapbox/rewrite-exit-destination-signage)

Rewrites OpenStreetMap [`exit_to=`](http://wiki.openstreetmap.org/wiki/Key:exit_to) Node tags on [`highway=motorway_junction`](https://wiki.openstreetmap.org/wiki/Tag:highway%3Dmotorway_junction) to [`destination=`](http://wiki.openstreetmap.org/wiki/Key:destination) tags on the adjacent way when possible to do so without ambiguity.

### Why

- Query for `exit_to` node tags, Bay Area: http://overpass-turbo.eu/s/kEM
- Query for `destination` way tags, Bay Area: http://overpass-turbo.eu/s/kEN

## Building

A recent libosmium is getting downloaded to `third_party` by invoking the `./deps.sh` script.

    ./deps.sh
    mkdir build && cd build
    cmake .. -DCMAKE_BUILD_TYPE=Release
    cmake --build .

## Using Mason

You can build this project using packages bundled with mason:

    ./masonize.sh
    mkdir build && cd build
    cmake .. -DCMAKE_BUILD_TYPE=Release -DENABLE_MASON=On
    cmake --build .

## Running

    ./exit2destination in.osm.pbf out.osm.pbf

## Tests

See the `tests` directory.

    pushd tests
    ./check.sh
    popd

## License

Copyright © 2016 Mapbox

Distributed under the MIT License (MIT).
