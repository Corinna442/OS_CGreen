## Lab 05

- Name: Corinna Green
- Email: green.442@wright.edu

## Part 1 

Make sure the following files are in your GitHub repository
- validator (with commits for each step complete)
- `clean1.txt` through `clean4.txt`

## Part 2 Answers

1. `sed -i 's/<\/[^>]*//g' sedfile.md`
2. `sed -i 's/[[:space:]]*<li>/-/g' sedfile.md`
3. `sed -i 's/^[[:space:]]*<li>/\-/g' sedfile.md`
4. `sed -i 's/<h1>/#/g' sedfile.md`
5. `sed -i 's/<u1>//g; s/<html>//g' sedfile.md`
6. `sed -i 's/Batches/Matches/g' sedfile.md`

## Part 3 Answers

1. `awk '$1 ~ /^Bil/ {print $1}' records.txt`
2. `awk '$4 == 42 {print $3}' records.txt`
3. `awk '/wright\.edu/ {print $2 ", " $1 ": " $3}' records.txt`
4. `awk '/wright\.edu/ && $6 == 1234 {print $2 " Last favorite number is: " $4}' records.txt`
5. `awk '{$6 = "N0T@PL@!NP@$$W0RD"; print}' records.txt > updaterecords.txt`
