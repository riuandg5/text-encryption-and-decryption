# text-encryption-and-decryption
Encrypt and decrypt text in C

ENCRYPTION
-----------------
--> Have some text input as string.

Ex--> RISHU

--> Add a pointer at the end of string.
    Ex--> RISHU|
--> Apply Burrows Wheeler Transformation.
    --> Get all possible rotations by one unit displacement.
        Ex--> |RISHU
              U|RISH
              HU|RIS
              SHU|RI
              ISHU|R
              RISHU|
    --> Arrange all rotations in lexical order.
        Ex--> HU|RIS
              ISHU|R
              RISHU|
              SHU|RI
              U|RISH
              |RISHU
--> String with last characters of lexicographically orderd rotations is the encrypted text.
    Ex--> SR|IHU
--> Could save the encrpted text in file.

DECRYPTION
-----------------
--> Have encrypted text as input or from a file and arrange in a coloumn.
    Ex--> S
          R
          |
          I
          H
          U
--> Arrange in lexical order.
--> Add up arranged coloumn with encrypted coloumn.
--> To get all possible rotations repeat previous two steps.
Ex--> Encrypted  Arrange   Add     Arrange   Add     Arrange   Add     Arrange   Add     Arrange   Add
       coloumn
      ---------  -------   ------  -------   ------  -------   ------  -------   ------  -------   ------
          S      H         SH      HU        SHU      HU|      SHU|    HU|R      SHU|R   HU|RI     SHU|RI
          R      I         RI      IS        RIS      ISH      RISH    ISHU      RISHU   ISHU|     RISHU|
          |      R         |R      RI        |RI      RIS      |RIS    RISH      |RISH   RISHU     |RISHU
          I      S         IS      SH        ISH      SHU      ISHU    SHU|      ISHU|   SHU|R     ISHU|R
          H      U         HU      U|        HU|      U~R      HU|R    U|RI      HU|RI   U|RIS     HU|RIS
          U      |         U|      |R        U|R      |RI      U|RI    |RIS      U|RIS   |RISH     U|RISH
--> In last add coloumn find string which ends with pointer.
    Ex--> RISHU|
--> Could store this decrypted text in file. 
