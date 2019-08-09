# friendnet.pl

![Maintenance](https://img.shields.io/maintenance/yes/2019.svg)


## Your social network on Goodreads.com

...


## Output

```console
$ head friendnet-nodes.csv friendnet-edges.csv
==> friendnet-nodes.csv <==
id,name,img_url
50963461,"Peter Hesel",https://images.gr-assets.com/users/1514444137p2/50911111.jpg
15234617,"Carole Orsifault",https://images.gr-assets.com/users/139552226262/15222217.jpg
41346336,"Jordan Tenner",https://images.gr-assets.com/users/1427180778p2/41444336.jpg
4113463,Tim,https://images.gr-assets.com/users/1432411115p2/4114553.jpg

==> friendnet-edges.csv <==
from,to
15413712,18523418
15413712,8252516
15413712,13162689
15413712,9348911
```

CSV-files can be easily processed with any social network analysis (SNA) 
software such as `R` with the `iraph` package.


## Social network analysis (SNA)

Network type: 
- Egocentric (not sociocentric/complete), 
- Directed   (not undirected), 
- Binary     (not valued), 
- One-Mode   (not bipartite/multi-mode), 
- Connected  (not disconnected)


![Network](img/friendnet.png?raw=true "Network")


```R
some examples with R and igraph
```

```console
some examples with q
```


## How to generate this on a GNU/Linux operating system

```console
$ git clone https://github.com/andre-st/goodreads.git
$ cd goodreads
$ sudo make        # Required Perl modules from CPAN
$ ./friendnet.pl --help
$ ./friendnet.pl goodlogin@example.com

Traversing #18418712's social network (depth=2)...
Covered: [100%, 100%] 
Writing network data to: 
./friendnet-18418712-nodes.csv  (N=22678)
./friendnet-18418712-edges.csv  (N=24899)

Total time: 47 minutes
```

**Note:**

You can break the process with <kbd>CTRL</kbd>-<kbd>C</kbd> and continue later
without having to re-read all online sources again, as reading from
Goodreads.com is very time consuming.  The script internally uses a
**file-cache** which is busted after 31 days and saves to /tmp/FileCache/.



## Observations and limitations

- long runtime: Goodreads slows down all requests and we have to load a lot of data



## Feedback

If you like this project, give it a star on GitHub.
Report bugs or suggestions [via GitHub](https://github.com/andre-st/goodreads/issues) 
or see the [AUTHORS.md](AUTHORS.md) file.


## See also

- [friendrated.pl](friendrated.md) - Books common among the people you follow
- [likeminded.pl](likeminded.md)   - Find Goodreads members with similar book taste
- [recentrated.pl](recentrated.md) - Know when people rate or write reviews about a book
- [similarauth.pl](similarauth.md) - Find all similar authors
- [search.pl](search.md)           - Sort books-search results by popularity or date published
- [savreviews.pl](savreviews.md)   - Get all reviews of a book

