# 🖥️ Irssi IRC Chat
## Install & Launch

```bash
# Install Irssi
sudo apt install irssi

# Launch Irssi
irssi
```

## Connect & Chat

Type these commands inside Irssi (one by one):

```irc
/connect irc.libera.chat
/nick YourNickname
/join #YourChannelName
```

## Make Your Channel Private (Password)

```irc
/mode #YourChannelName +k YourPassword
```

Your friend joins with:

```irc
/join #YourChannelName YourPassword
```

## Basic Commands

| Action | Command |
|--------|---------|
| Send message | Just type and press Enter |
| Private message | `/msg FriendName Hello` |
| Change nickname | `/nick NewName` |
| Leave channel | `/part #ChannelName` |
| Quit Irssi | `/quit` |

## Pro Setup: Stay Online 24/7

On a cheap VPS:

```bash
ssh user@your-vps-ip
sudo apt install irssi tmux
tmux new -s irc
irssi
```

Detach: `Ctrl+B` then `D`

Reattach: `tmux attach -t irc`

## Need Help?

Type `/help` inside Irssi. Type `/quit` to exit.

---

**Done. You're chatting.**
