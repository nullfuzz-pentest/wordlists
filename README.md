# wordlists

===[ Start Fuzzing ]===

ffuf -w common.txt:FUZZ -w ~/bb/target/httpx.txt:URL -u URL/FUZZ -mc 200 -of csv -o ffuf-result.txt

===[ See The Result ]===

cat ffuf-result.txt | awk -F ',' '{print $3}'

N.B: My wordlist have '/' at beginning
Example: /.git

If your wordlist start with '.git'
use like this -u URL/FUZZ
