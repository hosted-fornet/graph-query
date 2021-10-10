# graph-query

## installation

to install from source:

in ship dojo:
```
:: set up `%graph-query` desk
|merge %graph-query our %base
|mount %graph-query
```

in bash:
```bash
# checkout the urbit repo
git clone https://github.com/urbit/urbit.git

# checkout the graph query repo
git clone https://github.com/h5gq3/graph-query.git

# copy make script into Urbit `pkg` dir
cd urbit/pkg
cp ../graph-query/scripts/make-graph-query.sh .

# run make script to populate `%graph-query` desk, setting
# `PATH_TO_PIER` to point to your ship pier
PATH_TO_PIER=/path/to/pier && ./make-graph-query.sh $PATH_TO_PIER ../../graph-query/src
```

in ship dojo:
```
:: install
|commit %graph-query
|install our %graph-query

:: publish, if desired
=dir /=garden
:treaty|publish %graph-query
```

## generator input arguments

```
resource=resource:g                             ::  group to query from
sq=(unit tape)                                  ::  search query word  :: TODO make case insensitive
author=(unit @p)                                ::  author of post
before=(unit @da)                               ::  cutoff posts after a timepoint
after=(unit @da)                                ::  cutoff posts before a timepoint
page=@ud                                        ::  one page of 420 posts from graph, page 1: queries 420 nodes, page 2: next 420 nodes etc.
```

## example query with generator

``+graph-query [~bitbet-bolbel %urbit-community] ~ `~tinnus-napbus `~2021.4.28 `~2021.4.10 1``

## shoe app usage

make sure to `|commit %home` (or other specified desk) inside dojo and then `|start %graph-query-cli`

then press `?` to see query options
