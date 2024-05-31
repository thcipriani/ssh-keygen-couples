ssh-keygen-couples
==================

This script takes an ssh public key file, extracts key data, and prints
fingerprints. The script displays key fingerprints as:

- SHA256
- MD5
- ASCII representation of the SHA256 hash
- Four couples names and cities inspired by a [2006 talk by Dan Kaminsky][0]

Usage
-----

    $ ./ssh-keygen-couples -f ~/.ssh/id_ed25519.pub
    SHA256:XrvNnhQuG1ObprgdtPiqIGXUAsHT71SKh9/WAcAKoS0
    MD5:2c:b8:ca:b7:07:4a:40:b7:30:42:91:6e:24:70:13:3f
    +-----------------+
    | .++ ...         |
    | o+.... o        |
    |. .oo=.o .       |
    | E .+.=   .      |
    |    o= .S.o.o    |
    |   o  o.o+.= +   |
    |  . .  .o B *    |
    |   . .   + & .   |
    |      ..+o*.=    |
    +-----------------+
    Key Data:
        Svasse and Tainen Jesudasson from Fort Wayne, Indiana, United States
        Illma and Sibeth Primack from Itārsi, Madhya Pradesh, India
        Maarja and Nisim Balyeat from Mukilteo, Washington, United States
        Hsu-Heng and Rasim Haozi from Manali, Tamil Nadu, India

Math
----

SHA256 key fingerprints are 256 bits. To represent this as couples, the math works like this:

- 131,072 first names: 17 bits per name (×2)
- 524,288 last names: 19 bits per name
- 2,048 cities: 11 bits per city
- 17+17+19+11 = 64 bits
- 4×couples = 256 bits

Credits
-------

- The names are the ascii first/last names in the dataset [A cross-verified database of notable people, 3500BC-2018AD][1].
- The cities are from https://github.com/datasets/world-cities.

[0]: <https://www.youtube.com/watch?v=QT2hOyK2qv4&t=599s>
[1]: <https://www.nature.com/articles/s41597-022-01369-4>
