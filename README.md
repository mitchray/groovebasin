# Groove Basin

Multiplayer music player for your home or office.

Run it on a server connected to your main speakers. Guests can connect with
their laptops, tablets, and phones, and play and share music.

Depends on [mpd](http://musicpd.org) for the backend. Some might call this
project an mpd client.

## Features

* Lightning-fast, responsive UI. You can hardly tell that the music server is
  on another computer.

* Dynamic playlist mode which automatically queues random songs, favoring
  songs that have not been played recently.

* Drag and drop upload. Drag and drop playlist editing. Rich keyboard
  shortcuts.

* Streaming support. You can listen to your music library - or share it with
  your friends - even when you're not physically near your home speakers.

## Dependencies

* [node.js](http://nodejs.org)

    After installing node.js, install [npm](http://npmjs.org) and then
    install node dependencies:

    ```
    $ sudo npm link
    ```

* [mpd](http://musicpd.org)

    Compile from source; we depend on some new stuff:

    ```
    $ git clone git://git.musicpd.org/master/mpd.git
    ```

* [sass](http://sass-lang.com) 3.1 or better. Make sure `sass` is in your PATH.

## Installation

1. Install, configure, and run mpd. Make sure you can get it to make noise.

2. Compile with `make`.

3. You can now run `./groovebasind` to start the server.

## Configuring

Some features require configuring to get working.

Configuration options can be set by placing a JSON file in `~/.groovebasinrc`.
You can see what the structure should look like at the very top of
`./src/daemon.coffee`.

You can also set any config options on the command line using dot syntax. For
example:

```
$ ./groovebasind --http.port 80 --mpd.conf ~/.mpd/mpd.conf
```

### Download Support

Softlink `./public/library` to your music folder.

### Streaming Support

1. In your mpd conf file, uncomment the "httpd" `audio_output` and configure
   the port. Recommended "vorbis" encoder for better browser support.

2. Restart mpd.

3. Add the correct `mpd.stream_url` to your `~/.groovebasinrc` config file.
   It should look something like `http://your.server.org:8000/mpd.ogg`

4. Be sure that both `http.port` and the streaming port are forwarded to your
   server in your router settings.

## Screenshots

![Searching library](http://www.superjoesoftware.com/temp/groove-basin-5.png)
![Multi-select and context menu](http://www.superjoesoftware.com/temp/groove-basin-2.png)
![Drag/drop support](http://www.superjoesoftware.com/temp/groove-basin-3.png)
![Keyboard shortcuts](http://www.superjoesoftware.com/temp/groove-basin-4.png)
![Drag and drop / multiselect upload](http://www.superjoesoftware.com/temp/groove-basin-1.png)

