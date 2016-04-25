

##Usage:

    Usage: xsstest.py [options]

    Options:
      -h, --help            show this help message and exit
      -u URL, --url=URL     target URL
      --post                try a post request to target url
      --data=POST_DATA      posta data to use
      --threads=THREADS     number of threads
      --http-proxy=HTTP_PROXY
                            scan behind given proxy (format: 127.0.0.1:80)
      --tor                 scan behind default Tor
      --crawl               crawl target url for other links to test
      --forms               crawl target url looking for forms to test
      --user-agent=USER_AGENT
                            provide an user agent
      --random-agent        perform scan with random user agents
      --cookie=COOKIE       use a cookie to perform scans
      --dom                 basic heuristic to detect dom xss


## Examples:

Scanning a single url with GET params:

    $ python xsstest.py -u "http://target.com/index.php?page=test"

Scanning a single url with POST params:

    $ python xsstest.py -u "http://target.com/index.php" --post --data=POST_DATA

Crawl a single url looking for forms to scan:

    $ python xsstest.py -u "http://target.com" --forms

Mass scan an entire website:

    $ python xsstest.py -u "http://target.com" --crawl

Mass scan an entire website forms included:

    $ python xsstest.py -u "http://target.com" --crawl --forms

Analyze target page javascripts (embedded and linked) to search for common sinks and sources:
    
    $ python xsstest.py -u "http://target.com" --dom

