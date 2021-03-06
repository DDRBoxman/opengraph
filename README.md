# [![Open Graph protocol](http://imgur.com/pqFdEuo.png?1)](http://ogp.me/) opengraph #

opengraph is a Go library for extracting Open Graph metadata from html documents.

**Documentation:** <http://godoc.org/github.com/rojters/opengraph>  
**Open Graph protocol:** <http://ogp.me/>  
**Build Status:** [![travis-ci status](https://api.travis-ci.org/rojters/opengraph.png)](https://travis-ci.org/rojters/opengraph) [![Build Status](https://drone.io/github.com/rojters/opengraph/status.png)](https://drone.io/github.com/rojters/opengraph/latest)  

## Usage ##

```go
import "github.com/rojters/opengraph"
```

To extract Open Graph metadata from a movie on IMDb:
```go
res, _ := http.Get("http://www.imdb.com/title/tt0118715/")
og, _ := opengraph.Extract(res.Body)
for _, md := range og {
	fmt.Printf("%s = %s\n", md.Property, md.Content)
}
```

Which will output:
```
url = http://www.imdb.com/title/tt0118715/
type = video.movie
title = The Big Lebowski (1998)
site_name = IMDb
description = Directed by Joel Coen, Ethan Coen.  With Jeff Bridges ...
...
```

## License ##

MIT
