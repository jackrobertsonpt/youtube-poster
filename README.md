# Youtube Poster github action

This is a very simple github action that will post to your youtube channel.

## Setup

Please see the setup steps on the pages:
- [setup-youtubeuploader github action](https://github.com/AnimMouse/setup-youtubeuploader)
- [youtubeuploader](https://github.com/porjo/youtubeuploader)

You'll need to configure two github secret variables called:

- `CLIENT_SECRETS_B64`
- `REQUEST_TOKEN_B64`

These are the Base64 versions of the client_secrets.json and request_token.json files.
 

## Usage:

This github action will run on a git push to the `main` branch. 

To run correctly, ONLY provide the URL of the video to download in the commit message. 

(There is an `if` statement to look for the text `https`)

This action will then publish the video to your channel with the details in the metadata.json file.

## Tools

This uses the GO tool [youtubeuploader](https://github.com/porjo/youtubeuploader) from porjo.

## metadata.json

An example of the metadata.json file would be:

```
{
  "title": "my test title",
  "description": "my test description",
  "tags": ["test tag1", "test tag2"],
  "privacyStatus": "private",
  "madeForKids": false,
  "embeddable": true,
  "license": "creativeCommon",
  "publicStatsViewable": true,
  "publishAt": "2017-06-01T12:05:00+02:00",
  "categoryId": "10",
  "recordingdate": "2017-05-21",
  "playlistIds":  ["xxxxxxxxxxxxxxxxxx", "yyyyyyyyyyyyyyyyyy"],
  "playlistTitles":  ["my test playlist"],
  "language":  "fr"
}
```
