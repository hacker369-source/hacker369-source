- 👋 Hi, I’m @hacker369-source
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
hacker369-source/hacker369-source is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
.sh
#!/data/data/com.termux/files/usr/bin/sh
# font changer
set -e -u

backup_font() {
	cp /data/data/com.termux/files/home/.termux/font.ttf /data/data/com.termux/files/home/.termux/font.ttf.bak
}

restore_font() {
	cp /data/data/com.termux/files/home/.termux/font.ttf.bak /data/data/com.termux/files/home/.termux/font.ttf
}

show_help() {
    echo 'Usage: font command'
    echo ''
    echo 'Use custom fonts in termux. Commands:'
    echo ''
    echo ' change <path to fontfile.ttf>'
    echo ' reset/restore (revert to previous font)'
    echo ' help (show this help message)'
    echo ''
    exit 1
}
if [ $# = 0 ]; then show_help; fi
CMD="$1"
shift 1

case "$CMD" in
	res*) restore_font;;
	change) backup_font; cp "$@" /data/data/com.termux/files/home/.termux/font.ttf;;
	*) echo "Unknown command: '$CMD'";;
esacip 
