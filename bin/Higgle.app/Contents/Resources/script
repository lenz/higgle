STATE=`defaults read com.apple.finder AppleShowAllFiles`

NEW_STATE=FALSE

if [[ $STATE == FALSE ]]; then
    NEW_STATE=TRUE
fi

ANSWER=`osascript -e 'tell app "System Events" to display dialog "This will relaunch Finder. Be shure no copy processes etc. are running to avoid data loss!"' 2> /dev/null`

if [[ $ANSWER == "button returned:OK" ]]; then
    defaults write com.apple.finder AppleShowAllFiles $NEW_STATE
    killall Finder
fi
