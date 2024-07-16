import spotipy
from spotipy.oauth2 import SpotifyClientCredentials

# Set up your client credentials
client_credentials_manager = SpotifyClientCredentials(client_id='your-client-id', client_secret='your-client-secret')
sp = spotipy.Spotify(client_credentials_manager=client_credentials_manager)

# Get the artist's URI
results = sp.search(q='artist:"Artist Name"', type='artist')
items = results['artists']['items']
if len(items) > 0:
    artist = items[0]
else:
    print("No artist found")
    exit()

# Get all the artist's albums
albums = sp.artist_albums(artist['id'], album_type='album')

# Get all the songs from the albums
songs = []
for album in albums['items']:
    album_songs = sp.album_tracks(album['id'])
    for song in album_songs['items']:
        songs.append(song['name'])

# Print all the song titles
for song in songs:
    print(song)
