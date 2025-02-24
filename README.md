# Crowd Sourced Security Platform's Programs

```bash
bugbountyprograms -O data
```

```bash
# List Program's Names
cat data/yeswehack-programs.json | jq -r '.[].name'

# List URLs 
cat data/yeswehack-programs.json | jq -r '.[].assets.[] | select(.type == "URL") | .identifier'

# Extract Root Domains
cat data/yeswehack-programs.json | jq -r '.[].assets.[] | select(.type == "URL") | .identifier' | xurl apexes --unique | xtee --unique root-domains.txt
```