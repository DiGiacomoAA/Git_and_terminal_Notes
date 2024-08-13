##LaTeX Troubleshooting

##### If SVG graphics aren't compiling/updating
```
xelatex -shell-escape -recache dissertation.tex
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
