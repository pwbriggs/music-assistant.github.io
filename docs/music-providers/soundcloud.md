# SoundCloud Provider

Support for Soundcloud as Music provider in Music Assistant contributed by @gieljnssns !

## How to get O-Auth and Client id

1. Delete your cookies for Soundcloud.
2. Go to [Soundcloud](https://soundcloud.com).
3. Open the `Inspect` tool (F12 on most browsers).
4. Go to the page `Network` on the inspect terminal.
5. Login.
6. Search for `auth`.
7. In one of the requests you will find `client_id` and `Authorization`

`client_id`: string of 32 bytes alphanumeric

`Authorization`: string that begins with O-Auth and a string (the o-auth token is "O-Auth . . .")

<img width="1005" alt="Scherm­afbeelding 2023-03-24 om 17 39 48" src="https://user-images.githubusercontent.com/17234951/227590129-b3c289fe-d9cc-4494-aa7c-c328a3b728a6.png">


Example code snippet (O-Auth and client_id are NOT real, use yours):

```
client_id = jHvc9wa0Ejf092wj3f3920w3F920as02
Authorization = O-Auth 3-26432-21446-asdif2309fj
```
## Notes

- Artists synced from Soundcloud are actually Soundcloud users.
- If a song by artist X is uploaded by user Y, this song belongs to the artist Y in Music Assistant
