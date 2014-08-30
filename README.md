# Simple CLI

A CLI tool for interacting with your Simple bank account.

*Note:* This is still under early development. The way argument parsing is handled and the available commands are subject to change before the 0.1.0 release (though it shouldn't change too much!).

## Installation

`sudo pip install https://github.com/nickpegg/simple-cli/archive/master.zip`

## Usage

### Examples
```
# Get last 20 transactions
simple -u nickpegg tail -n 20
 
# Get last 5 transactions and display any new ones as they appear in your account
simple -u nickpegg tail -n5 -f

#Check the status of your goals
simple -u nickpegg goals

# If you use a command-line password manager, such as password-store, 
# you can use it to pass the password into simple-cli via standard input, like this:
pass show simple | simple -u nickpegg -p goals
```

### Full Usage
```
Usage:
    simple [options] balances
    simple [options] tail [-n <num>] [-f]
    simple [options] goals [--archived] [--completed]
    simple [options] payments
    simple [options] card
    simple (-h | --help)
    simple --version

Options:
    -u <username>   Specify a Simple username to use
    -p              Supply a password via stdin
    -o [format]     Use <format> to output data [default: human]

Commands:
    balances        Display your account balances
    tail            Display a number of your latest transactions
    goals           Display your goals
    payments        Display your upcoming payments
    card            Display info about your Simple debit card

Tail Options:
    -n <num>        Get the <num> latest transactions [default: 10]
    -f              Display transactions as they're made, similar to the `tail -f` command

Goals Options:
    --archived      Show archived goals
    --completed     Show completed goals

Formats:
    human   Human-friendly output of the most important parts of the data
    raw     Raw output of the data
    pprint  Pretty-printed output of the data
    json    JSON dump of the data
```
