# jira-timetracking-cli

This tool can be used to book times into JIRA issues. This tool uses the internal rest api (v3) of JIRA and therefore can be subject to change. Use it on your own risk!

## Installation

`pip install jira-timesheet-cli`

## Usage

Before using the tool you need to specify the following environment variables:
- JIRA_URL: The jira base url. Eg. `https://jira.test.com/`
- JIRA_USER: Your JIRA user (eg. email address)
- JIRA_TOKEN: Your API access token 

See help for more information about the arguments: `book-time -help`. Examples:
```
book-time -yesterday -ticket ABC-1234 -duration 3h15m -at 18:45
book-time -today -ticket ABC-1234 -duration 3h15m -at 14:45
book-time -ticket ABC-1234 -duration 3h15m -date 28-10-22 -now
book-time -ticket ABC-1234 -duration 3h15m -date 28-10-22 -at 08:45
```

If you don't want to set a specific time and instead always book at the same time, you can just use an alias:
```
alias book-time='book-time -at 10:00'
```

## Completion

`source <(book-time completion)`
