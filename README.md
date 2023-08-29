# AI Spotify Playlist Generator

This tool allows you to generate a Spotify playlist of songs based on a text prompt using the ChatGPT language model. It leverages the OpenAI GPT-3.5 Turbo model and the Spotipy library to create playlists of your desired length.

## Prerequisites

Before using the tool, you need to set up the necessary credentials and environment variables:

1. **Spotify API Credentials**: You need a Spotify Developer account and create an application to obtain the `SPOTIFY_CLIENT_ID` and `SPOTIFY_CLIENT_SECRET` credentials.

2. **OpenAI API Key**: Obtain an OpenAI API key to make requests to the GPT-3.5 Turbo model.

3. **Environment Variables**: Create a `.env` file in the same directory as this script and set the following environment variables:

   ```bash
   SPOTIFY_CLIENT_ID=<Your Spotify Client ID>
   SPOTIFY_CLIENT_SECRET=<Your Spotify Client Secret>
   OPENAI_API_KEY=<Your OpenAI API Key>
   ```

## Installation

1. Install the required Python packages using `pip`:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

Run the script with the desired options to generate a playlist:

```bash
python playlist_generator.py -d "<Playlist Description>" [-p "<Playlist Name>"] [-n <Number of Songs>]
```

- `-d`: The description that will be used as a prompt for generating the playlist.
- `-p`: (Optional) The name of the playlist. If not provided, a default name will be generated.
- `-n`: (Optional) Number of songs to include in the playlist. Default is 10 songs.

For example:

```bash
python playlist_generator.py -d "Upbeat summer vibes" -p "Summer Jams" -n 15
```

## Workflow

1. The script initializes the environment by loading the necessary environment variables and API keys.

2. It parses the command-line arguments to determine the playlist description, name, and length.

3. The tool generates a list of songs and their artists based on the provided description using the ChatGPT model.

4. The script authenticates with the Spotify API using the provided credentials.

5. It searches for each song in the generated list on Spotify to retrieve track IDs.

6. A new private playlist is created on the user's Spotify account and the retrieved track IDs are added to the playlist.

7. Upon successful playlist creation, the script logs the details of the generated playlist.

## Notes

- The generated playlist will be private by default.
- The ChatGPT model may sometimes return unexpected song suggestions, so you may need to fine-tune your prompts for better results.

## Disclaimer

This tool relies on external APIs and services (OpenAI and Spotify) and is subject to any limitations, rate limits, or changes imposed by these platforms.

## License

This project is licensed under the terms of the MIT License. See the [LICENSE](LICENSE) file for details.
