---
author: "icarnaghan"
title: "Building a Multi-drop Link"
date: 1999-10-28
categories: 
  - "coding"
---

Computers play a vital role in the commercial world today as I.T. advancements mean newer tools and facilities available in all industries.  However without the means of communications between workstations within a computer network, the distribution of information would not be as straightforward as it has now become.

When looking at how this type of communication is possible, it is necessary to examine the physical hardware and software processes involved.  A multi-drop link is quite simply a very basic communication device that enables multiple Personal Computers to interconnect with each other.  This is made possible through a special chip found inside all Intel x86 PC’s called the Universal Synchronous / Asynchronous Receiver / Transmitter (USART).  This chip allows two important processes that are required for any type of two-way communications.  Input and Output of data can be sent to and from this chip which therefore makes it possible to build a link to another of it’s kind.

A combination of hardware to make the bridge between the different PC’s and software written specifically in a low level language that is vital in order to control this hardware, form the basis of the Multi-drop link.  Once complete, the multi-drop link could send signals between the various PC’s interconnected which could be interpreted as data and hence the information sent would form the basis of a computer network.  The main focus of this report is on the creation of a multi-drop link and the processes involved in programming it to enable transfer of data between multiple PC’s.

## Initial Construction

The team I worked with on this project were initially issued a breadboard (Prototyping board) and several components to combine in order to construct the multi-drop link.  We agreed to build the link in sections so everyone would be able to follow the processes to obtain the end result.

Firstly it was noted that there were two main chips that were required for the link.  These consisted of a MAX485 and a MAX 233.  The MAX233 chip is necessary to convert the RS232 voltage levels (+12v, -12v) to TTL levels (0 and 5v), which is required to power the board, and the MAX485 acted as the main line driver to and from the PC connection.  Several pins of each chip were connected to each other as well as other components that were build onto the breadboard.  A voltage regulator was necessary to reduce noise during input/output processes. Other components used consisted of several diodes, capacitors and LEDs (Light Emitting Diodes) to show the output results on the board.

Once the circuit was complete, it was necessary to interface it with a PC in order to test if it was fully operational.  This was accomplished through using an interface – bus which in turn was connected directly to the USART chip inside the PC through its external serial port (COM 1).  The bus comprising of different wires connected to the interface was interconnected to different parts of the circuit board we had created.

In order for the circuit to operate correctly it required a certain amount of power.  Instead of supplying an external power supply to feed the board we were able to directly borrow a small amount of power, +5 volts, from the PC through the DTR connection of the USART chip.  The DTR is software controlled and can be set from –12 volts to + 12 volts, so in order for our circuit to function properly it had to be set correctly.  This connection was made directly by the bus connection from the serial port of the PC to the top layer of the breadboard, which supplied the rest of the circuit with power.  The bottom layer of the breadboard provided the earth, which we required for the circuit.

Once the circuit was completely compiled, the next task was to implement the software in order to control it.  The software was written in the low-level language C, which is best suited for direct hardware control.  Our program would simply send a series of binary code 0s and 1s to and from the computer from the circuit and the output would be produced through the LEDs.  When the program was written and compiled, our group ran it for the first time and thankfully the result was positive.  The program was initially designed to produce output on the board in the form of the two LEDs flashing alternatively, while giving an output on the PC showing a series of AAs. We achieved the output once the program ran proving the link worked correctly.

Finally the link was complete and worked perfectly between the breadboard circuit we built and the PC it was connected to.  We had determined that 0 was represented by the green LED while 1 was represented by red.  The next step was to adjust some of the settings and test different outputs to find the outcomes of the changes.  The change we made involved altering some of the program code in the _void main()_ function _unsigned char stuff=0xAA_.  This value was initially changed to 0xFF – once the program was compiled and ran again, the two LEDs flashed alternatively but the green stayed on for longer and the red only for a split second.  To further test this, the value was then changed to 0x00 – this had the opposite effect whereby the red LED was lit for longer and the green flashed for a split second.

From our results we concluded that the higher the value, the longer the green LED was allocated on time while the red was allocated a far less time to show output.  The lower the value was the opposite to the above, where the red was allocated more time and the green less.  Therefore the statement was linked directly to time allocation of the LEDs.

The next test to make was to change the baud rate of the board.  This would show if there would be a significant change on the output, which should logically adjust depending on the rate set.  This was a simple matter of adjusting the baud setting within the _void main()_ function of the program.  The line initially read _int baud=2_ so we changed this to a higher value 20.

From the result we achieved from this change, it was clear to see that the transfer rate had increased because both LEDs were flashing alternatively a lot quicker than before.  From what we could determine it looked like they were flashing exactly twice as quick which would explain the increase in the baud rate we had made.  We tested further by increasing the value more to 9600, the old standard for fax machine transmission.

At this speed the LEDs lit on and off so quickly it appeared that they were both permanently lit.  We concluded that the higher the baud rate – the faster the LEDs lit, hence the faster the transfer rate became.

Finally we had a completed communication device controlled by computer software that we could manipulate and change according to our requirements.  The next step was to build a link between two boards and create a network.  This would show the full use of data transmission between two or more computers linked together in a network.

## Using the Multi-Drop Link

In order to link two or more computers together using a multi-drop link it was necessary to make some modifications on the previous work we had produced.  Initially we would have to write a new program in order to control the data between two PCs.  Next we would have to modify our board to link to another.  The idea behind the link was to create a one way link from a sending computer to a receiving computer.

The main problem we had to begin with was the fact that only one board was created in our group in the first session as two of our team members did not show up for any of the lab sessions.  We initially decided to build two circuits in groups of two instead of three, but there seemed to be a lack of bread boards and components available.  It wasn’t until 35-40 minutes into the first session that we finally managed to acquire components to make one board, so obviously it wasn’t feasible to construct two boards during that session.

To build a link between two PC’s required two constructed boards that would communicate to each other through the modifications that would be necessary both for the hardware and software.  Unfortunately all the other groups had two boards between them so they could start immediately whereas our group could do nothing but wait until another group had finished to test the link.

In the meanwhile we programmed the new software that would be required by the link to transmit the data from one computer to the other.  We also had to make necessary changes on our circuit board that included the link of a twisted pair cable, which would eventually link to another board when it became available.  This link would form the basis of the network we were attempting to create between the two computers.  Basically the data from the sending PC would be sent to the board that was attached to the USART and this would be transmitted to the second board which would in turn send this to receiving PC it was connected to.  This type of communication is known as Simplex - one way communication from one entity to another.

It wasn’t until an hour and a half through the second lab session that we could finally make a start on the link.  We were issued with a circuit board that needed to be rebuilt.  It was our intention to rectify the problems with this board and create the link within the small amount of time we had left.

Our group worked quickly and we eventually managed to complete the circuit and link it to our original.   We already had the software completed from earlier, so we decided to run the program.  The first observation made was that whenever any key was struck on the keyboard of the sending computer, a series of flickers came from the LEDs indicating a binary pattern, which obviously represented the character sent.  The receiving computer however did not seem to obtain any of the data sent.   Unfortunately the link did not work correctly, but just before the lab session was about to end another group had finished and let us link with their circuit.  The result was positive and although the correct characters didn’t appear on the receiver’s monitor, the link was made and it was only a small error that could easily be corrected.

## Improving the Multi-Drop Link Protocol

Unfortunately because our group was pressed for time towards the end of the second lab session, we never managed to look into ways of improving the multi-link protocol.

However, from what we did achieve, it was obvious on improvements that could have been made on our board.  Unfortunately because we never constructed the two-way link (both computers able to send to each other) our link was a only one directional – simplex communication.

In order to improve this we would have modified it to make it a duplex two-way connection.  I would like to have examined other areas such as increasing the speed of the connection further and possible ways of encrypting information sent from one machine to another.  Encryption is a vital part of any computer network that requires sending and receiving sensitive data that should be protected from unauthorised access.

### Results and Conclusion

In today’s world of communications and the Internet especially, many people take the principles of communications for granted.  Both sessions have taught me to appreciate the actual workings of how PCs can communicate between one another. The first session helped me to learn about prototyping boards and how to create a circuit from specific wired diagrams.  It was interesting to see if we had constructed it correctly, and we had a lot of success.  We learned how to change the settings of our communication device through the software that controlled it.  I feel I gained a greater understanding of the devices used such as the actual USART connection through the computers serial port and the two main chips, MAX233 and MAX485, which formed the main part of the circuit.

During the first session I was mainly involved in creating the board as I had a great interest in obtaining results from the communication device we were attempting to create.  Two of the other group members worked on typing up the code that would inevitably control the board we were creating.

Unfortunately, because of difficulties we had during the second lab which was outlined earlier in the report, I feel we could have achieved much more.  We managed to create the link between two PC’s before the end of the Lab Session so there was a certain element of success.

However the link we created was only a Simplex connection.  I would have liked to implement a two way link forming a duplex connection between the two PCs.  We never actually managed to connect to more than two computers so although we formed a network with what we had, I feel that there was so much more we could have investigated.

During this session, I was mainly involved in assisting to rebuild the uncompleted board we were issued towards the end of the lab session.  I feel a great amount of time was wasted during this session as our group had asked several other people for assistance to link to another group, but unfortunately there was nothing that could be done about it.  For the first hour and a half we had to wait until another board became free to link to but I believe our group were very productive during the last section of the lab session as we managed to get the link up and running very quickly meeting the deadline.

Appendix

### Lab Session 1 (Changes in First Program)

Changing Data (stuff=0x0aa)

**Before Change**

unsigned char stuff=0xAA

**Change 1**

unsigned char stuff=0xFF

Resulted in green LED being lit for longer period and red less

**Change 2**

unsigned char stuff=0xAA

Resulted in red LED being lit for longer period and green less

**Changing Baud Rate** 

BEFORE CHANGE int baud = 2

CHANGE 1 int baud = 20 Resulted in an increased baud rate and LED’s flashed quicker giving a greater data transmission rate

CHANGE 2 int baud = 9600 Resulted in a greater increased baud rate (same rate as old stand for fax machines) LED’s appeared permanently on because transmission rate so high

### Lab Session 2 (Changes in Second Program)

**RECEIVING COMPUTER / HOST – ADDITIONAL LINES ADDED**

```
void main()
{
      int BaudRate= 32;
      unsigned char chin;
      int event;

      init_port (BaudRate);
      outp(MODEM_CTL, 0x03);
      while (1 == 1)
      {
            event = status();
            if (event & EVENT_CHAR_RECEIVED)
            {
                  chin = inp(DATAIN);
                  printf(“[%02X]”,  chin);
            }
      }
}

Sending Computer / Host - Additional Lines Added
```

```
void main()
{
      int BaudRate=32;
      unsigned char chout;
      int event;

      init_port (BaudRate);
      while (1 == 1)
      {
            event = status();
            if (event & EVENT_READY_TO_SEND)
            {
                  if (kbhit())
                  {
                        chout=getch();
                        outp(MODEM_CTL, 0x01);
                        outp(DATAOUT,chout);
                        printf(“(%c)”,chout);
                  }
                  else
                  {
                        outp(MODEM_CTL,0x03);
                  }
            }
      }
}
```
