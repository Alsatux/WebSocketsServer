"""
	WSS Project - WebSockets Server and Client

	Copyright (C) 2012 Jean Luc Biellmann (contact@alsatux.com)

	Widely inspired from:
	WebSocket client library for Python - Hiroki Ohtani(liris) - 2010

	This library is free software; you can redistribute it and/or
	modify it under the terms of the GNU Lesser General Public
	License as published by the Free Software Foundation; either
	version 2.1 of the License, or (at your option) any later version.

	This library is distributed in the hope that it will be useful,
	but WITHOUT ANY WARRANTY; without even the implied warranty of
	MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
	Lesser General Public License for more details.

	You should have received a copy of the GNU Lesser General Public
	License along with this library; if not, write to the Free Software
	Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA
"""

WebSockets Server (Python) library and Client (HTML) - version 1.0 - 2012

Version supported : 13 (RFC 6465 - http://tools.ietf.org/html/rfc6455)

SCHEME:

  WSMain (Startup)   incoming datas
    |                       |
    v                       v
WSServer (listen) => WSClient (thread) -> WSDecoder (one per WSClient)
    ^                       ^                  |
    |                       |                  |
    |                       |                  |
    |                       |                  v
    |                       |        	 WSController (one per WSClient)
    |                    unicast               |
    |                       |                  |
    |                       |                  |
    |                       |                  v
    |-------multicast-------|------------- WSEncoder

Remember : FIREFOX NEEDED !

HOWTO
-----

1) Start the server :
- Open a console
- Go to the uncompressed directory
- Type "python WSMain.py"

2) Start one or more clients :
- Rename the index.html file if needed
- Place the file to your favorite webserver (Apache or other)
- Open Firefox
- Point to the file - if all right, you should read a "CONNECTED" message

Settings
--------

You can change host, port and maxclients directly in WSMain.py.
