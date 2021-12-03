# linux-shell-scripts
useful shell scripts to help those everyday tasks

## quick dig lookup
#!/bin/bash
dig +nocmd $1 A +multiline +noall +answer
dig +nocmd $1 MX +multiline +noall +answer
dig +nocmd $1 TXT +multiline +noall +answer
dig +nocmd $1 NS +multiline +noall +answer%  


## load up NG project
#!/bin/bash
PS3='What Project would you like to serve? '
options=("Demo" "NextDemo" "Quit")
select opt in "${options[@]}"
do
cd /Volumes/Demo/sites/Frontend
    case $opt in
        "Demo")
            ng serve demo --configuration=development
	        echo "Serving Demo";
            ;;
        "NextDemo")
            ng serve mydemo --configuration=development
	        echo "Serving NextDemo";
            ;;
        "Quit")
            break
            ;;
        *) echo "invalid option $REPLY";;
    esac
done
