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
options=("Remax" "MyReNet" "RMA Network" "Dev Server" "Colliers" "FlightDeck" "Quit")
select opt in "${options[@]}"
do
cd /Volumes/ReNet/sites/renet/Frontend
    case $opt in
        "Remax")
            ng serve remax --configuration=development
	        echo "Serving Remax";
            ;;
        "MyReNet")
            ng serve myrenet --configuration=development
	        echo "Serving My ReNet";
            ;;
        "RMA Network")
            ng serve rma --configuration=development
	        echo "Serving RMA Network";
            ;;
        "Dev Server")
            ng serve dev --configuration=development
	        echo "Serving Dev Server";
            ;;
        "Colliers")
            ng serve colliers --configuration=development
	        echo "Serving Coronis";
            ;;
        "FlightDeck")
            ng serve flightdeck --configuration=development
	        echo "Serving FlightDeck";
            ;;
        "Quit")
            break
            ;;
        *) echo "invalid option $REPLY";;
    esac
done
