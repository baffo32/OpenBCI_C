# OpenBCI_C

C driver for OpenBCI boards.  A work in progress.

This branch is about modeling the API off of https://github.com/OpenBCI/OpenBCI_NodeJS/ for consistency.

##Building

```
./configure
make
```

##Running

`./test`

In order to communicate with the board, you currently must `echo` directly to the board. For example...<br/>
`echo -n 'b' > /dev/ttyUSB0` to start streaming <br/>
`echo -n 's' > /dev/ttyUSB0` to stop streaming <br/>

Any other character can be sent, however only certain characters will do things to the board. Check out http://docs.openbci.com/software/01-OpenBCI_SDK for more info.

##To-Do

- [ ] Provide primary functions of NodeJS API
  - [ ] Review https://github.com/OpenBCI/OpenBCI_NodeJS/ SDK information and lay out a rough outline in a header file.
    - [ ] Constructor
    - [ ] Methods
    - [ ] Events (callbacks)
    - [ ] Properties
    - [x] Constants are stored in openBCIConstants.js
  - [ ] Review .js implementation files at above URL with intention of copying some of the implementation.  Enumerate files in a TODO list here to track which have been processed, and how much.
    - [ ] openBCIBoard.js
    - [ ] openBCIConstants.js
    - [ ] openBCISample.js
    - [ ] openBCISerialFormat

- [ ] Implement tests
- [ ] Implementations with: Python, Labstreaminglayer, Matlab, Java/Processing

##Known Bugs
- [ ] Stock board does not reset properly on start and may occasionally begin streaming in a corrupt manner.  Library does not detect this.
