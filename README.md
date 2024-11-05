#IoT Repo

This repo houses tools and widgets designed by Ian Caple, to help illustrate and understand the logic behind the IoT assessment.

dpkencrypt and dpkdecrypt help to illustrate the logic behind what happens when executing a button press on during the assessment domenstration including the generation of the derived key (DPK).

# Psuedo Logic:

# On Sender Microbit:

Press Button A --> Generate string  A = Press Button A

Generate DPk --> capture salt used to create DPK.

Use DPK to encrypt String A using AES ECB (You'll need to find a AES Lite library such as embedded TLS or tiny-aes) --> Create Cipher A.

Send Salt + Cipher A to Receiver Microbit.

# On Receiver Microbit

On receipt of packet from Sender:

Unpack Salt to Generate Receiver DPK --> Decrypt Cipher A using DPK to recreate String A.

Upon receipt of String A --> Execute Command A (Command is what ever command of yur demonstration linked to Press Button A.)

# Note: It's worth breaking the problem down into logical steps like this and then writing the code for each step in order.

# Logic for the key generation can be found in the assessment. Again break it down stage by stage. Write the code to create k1, then k2 etc etc. Each section is reasonably straight forward and only a few lines of code.

# If you break the problem down it's a lot easier to manage that trying to get your head around a larger complex problem.
