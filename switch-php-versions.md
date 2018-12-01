## Switch php7.0 to php7.2 (switch_php72.sh)
```
#!/bin/bash
brew unlink php@7.0 && brew link --force --overwrite php@7.2
echo 'export PATH="/usr/local/opt/php@7.2/bin:$PATH"' >> ~/.zshrc
echo 'export PATH="/usr/local/opt/php@7.2/sbin:$PATH"' >> ~/.zshrc
launchctl unload -w /usr/local/Cellar/php@7.0/7.0.32/homebrew.mxcl.php@7.0.plist
launchctl load -w /usr/local/Cellar/php72/7.2.12/homebrew.mxcl.php.plist
```

## Switch php7.2 to php7.0 (switch_php70.sh)
```
#!/bin/bash
brew unlink php@7.2 && brew link --force --overwrite php@7.0
echo 'export PATH="/usr/local/opt/php@7.0/bin:$PATH"' >> ~/.zshrc
echo 'export PATH="/usr/local/opt/php@7.0/sbin:$PATH"' >> ~/.zshrc
launchctl unload -w /usr/local/Cellar/php72/7.2.12/homebrew.mxcl.php.plist
launchctl load -w /usr/local/Cellar/php@7.0/7.0.32/homebrew.mxcl.php@7.0.plist
```
