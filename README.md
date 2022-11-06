# macos-automator-character-count
macOS Automator Quick Action to count words and characters via Services 

```
on run {input, parameters}
	
	tell application "System Events"
		set _appname to name of first process whose frontmost is true
	end tell
	set word_count to count words of (input as string)
	set character_count to count characters of (input as string)
	tell application _appname
		display alert "" & word_count & " words, " & character_count & " characters"
	end tell
	
	return input
end run
```

<img width="609" alt="Automator count words and characters" src="https://user-images.githubusercontent.com/50701/200184849-0125f9b4-9c62-4b49-b793-be88aa397448.png">
