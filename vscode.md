# VS Code

<br/> <br/>

## Snippets
Super handy for auto-completion/tab-completion of boilerplate code. Can be scoped to language, project, or as global setting. There is [a ton of versatility available](https://code.visualstudio.com/docs/editor/userdefinedsnippets), but the short of it is, within a scoped `...code-snippets` file add, 

```json
	"Insert spacer line": {
		"prefix": "newline",
		"body": "<br/> <br/>",
		"description": "Insert a blank line for better readability in raw markdown."
	}
```

Then, `cmd+i` brings up intellisense, including snippets.


<br/> <br/>


## Make VS Code the default editor
- Add the following env var to bash profile
    - `export EDITOR="code -w"`
- In VS Code, install the `code` command to PATH
    - `cmd + shift + p`
    - search for `code`
    - select `Shell Command: Install 'code' command in PATH.` 
- Source bash profile and validate
    - `source ~./bash_profile`
    - `code local_file.py`
