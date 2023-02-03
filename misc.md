# Miscellaneous 

<br/> <br/>

## Run brew install without updates
Homebrew likes to update all taps be default. This can become tedious in cases where a simple install turns into a 30 minute system update. To turn off this behavior

- Set the following env var in bash profile
    - `export HOMEBREW_NO_AUTO_UPDATE=1`