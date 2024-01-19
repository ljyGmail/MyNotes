
## get all the cowsay images
Save all the possible cowsay image options in a text file `cowsay -f <tab>` 
```bash
cat shape.txt | grep -Eo '[a-z-]{1,}' | awk '{ print "echo", $0, "| cowsay -f", $0}' | bash | less
```