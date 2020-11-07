# Spotlightify

Spotlightify is a GUI based application designed to allow users to quickly interact with the Spotify Desktop application across Windows, Linux and macOS.

![Spotlightify](preview.gif)

## Prerequisites

-   Spotify Premium Account
-   Python 3.7 or later
-   A Spotify App must also be created, the instructions follow:
    1. Open the Spotify Developer Dashboard <a href="https://developer.spotify.com/dashboard/login" target="_blank">here</a> and login using your Spotify account credentials.
    2. Click the "CREATE AN APP" button.
    3. Name the application "Spotlightify", write anything for the description and select "Desktop App" from the checkboxes. Click "NEXT".
    4. Respond with "No" to the question "Are you developing a commercial integration?".
    5. Tick all boxes and click "SUBMIT".
    6. Now on the dashboard, click "EDIT SETTINGS".
    7. Under the title "Redirect URIs" enter: "http://localhost:8080", hit "ADD" and then at the bottom, hit "SAVE".
    8. That is the App set up, keep the dashboard webpage open as we will need `Client ID` and `Client Secret` from it later on.

## Installing Dependencies

### OS Specific Setup

To setup a virtual environment, perform the following commands.

#### Windows

```
cd path\to\spotlightify-root
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

#### MacOS

```
cd path/to/spotlightify-root
python -m venv venv
. venv/bin/activate
pip install -r requirements.txt

```

#### Linux

```
cd path/to/spotlightify-root
python3 -m venv venv
. venv/bin/activate
sudo apt-get install python3-pyqt5
pip3 install -r requirements.txt

Configure a service to auto start up Spotlightify:

cp spotlightify.service /etc/systemd/service (Make sure you're in the Spotlightify root dir)
sudo systemctl daemon-reload
sudo systemctl start spotlightify.service
sudo systemctl enable spotlightify.service

```

### Linking the Spotify App

Run `app.py` to start the application.

On the Spotify App that you have created, take the values of `Client ID`, `Client Secret` and `Redirect URI` (Redirect URL is found when the "EDIT SETTINGS" button is clicked) from the website and input them into their respective textboxes. To make sure the correct username is entered into the `username` textbox, go to <a href="https://www.spotify.com/us/account/overview/" target="_blank">this link</a>, get your exact username string and paste it (you only need to do this if you sign into Spotify using a service such as Facebook).

### Installing Fonts

The fonts found in `assets/fonts` must be installed for this to display correctly.

## Usage

The GUI is activated by using the shortcut `ctrl + space`. Here is the current list of available functions:

### List of Commands

```
| Name     | Description                                | Prefix            | Parameter     |
|----------|--------------------------------------------|-------------------|---------------|
| Play     | Plays a song                               | play              | song name     |
| Queue    | Queues a song                              | queue             | song name     |
| Playlist | Plays a saved/followed playlist            | playlist          | playlist name |
| Album    | Plays a saved album                        | album             | album name    |
| Artist   | Plays songs from a saved/followed artist   | artist            | artist name   |
| Liked    | Plays saved/liked music                    | liked             | None          |
| Volume   | Changes music volume                       | volume            | 1 - 10        |
| Go to    | Seeks a position in a song                 | goto              | e.g. 1:24     |
| Resume   | Resumes music playback                     | resume, start     | None          |
| Skip     | Skips the current song                     | skip, next        | None          |
| Previous | Plays pervious song                        | previous          | None          |
| Pause    | Pauses music playback                      | pause             | None          |
| Shuffle  | Toggles shuffle playback                   | shuffle           | None          |
| Device   | Select device for music playback           | device            | None          |
| Repeat   | Toggles repeating modes                    | repeat            | None          |
| Current  | Provides currently playing song info       | currently playing | None          |
| Share    | Copies the current song's URL to clipboard | share             | None          |
| Exit     | Exits the application                      | exit              | None          |
```

**On first start up, Spotlightify will cache all of your liked and playlist songs, caching both song information and album art. So keep the app open for at least 10 minutes so that all your songs can be cached.**

## Additional Information

### Built With

-   <a href="https://spotipy.readthedocs.io/en/2.12.0/" target="_blank">Spotipy</a> - A Spotify API wrapper for Python
-   <a href="https://www.riverbankcomputing.com/software/pyqt/" target="_blank">PyQt5</a> - A cross platform GUI framework for Python

### Contributing

Join us on <a href="https://discord.gg/nrDke3q" target="_blank">discord</a> to discuss how to contribute to the project.
