# This Script was made by Prime Security
# Please enjoy and remember we are not 
# responsible for any misuse or illigal
# use of this tool
#
#
# SynFlood
Start a SYN flood attack to an ip address.

## Requirements
- libnet1. `libnet1-dev` under Debian.
- Root access for sending a packet.
- Its recommended to block all RST packets from the source host on the source host.

		iptables -I OUTPUT -p tcp --dport 80 --tcp-flags RST RST -j DROP
		iptables -I OUTPUT -p tcp --dport 80 --tcp-flags RST ACK -j DROP

## Build

1. Clone:
	
		git clone https://github.com/PrimeSec420/synflood.git

2. In `synflood` directory, make:
	
		mkdir -p build && cd build && cmake -DCMAKE_BUILD_TYPE=Release .. && make && make test

3. Done.

## Usage

	./synflood SRC DST DPT [CONNECTIONS]

- `SRC`: Source IP address.
- `DST`: Destination IP address.
- `DPT`: Destination port.
- `CONNECTIONS`: Number of connections.

Examples:

	./synflood 192.168.241.31 192.168.1.3 80
	./synflood 192.168.241.31 192.168.1.3 80 1000

## Links
- [PrimeSecurity Repository](https://www.github.com/PrimeSec420)

## License
Copyright (C) 2019 Prime Security

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.
