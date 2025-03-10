##LaTeX Troubleshooting

##### If SVG graphics aren't compiling/updating
```
xelatex -shell-escape -recache dissertation.tex
```

To use Inkscape with LaTeX, you need to make sure the inkscape command is available in your terminal.

If Inkscape is not accessible from the terminal, you can create a symbolic link to make it available.

Run this command in the terminal:
```
sudo ln -s /Applications/Inkscape.app/Contents/MacOS/inkscape /usr/local/bin/inkscape
```

##### If biber not creating .bbl file
```
rm -rf `biber --cache`
```

##### If Package not installing/recognized
```
cd /Users/alexandria/Library
tlmgr --usermode install PACKAGENAME
```

```
#Install pygmentize via homebrew

# Create symbolic link for pygmentize
ln -s "$(which pygmentize)" /Library/TeX/texbin/pygmentize 
```
