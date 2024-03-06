
# Troubleshooting Guide 

When once service is not able to talk to other service , here are the possible reasons!!!!

1) Check whether the service is up or not
2) If the service is up, then check the status of the port and it should be opened on 0.0.0.0 and should be in LISTEN'ing state

3) If you Catalogue is still not able to talk to MONGO  . . . .

    Source      : Catalogue
    Destination : Mongod       ( 27017 )

    On the source machine, 
        $ telnet  destinationIPAddress  27017 
