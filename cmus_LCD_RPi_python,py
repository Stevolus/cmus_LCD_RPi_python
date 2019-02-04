#!/usr/local/bin/python3

import subprocess

def readable_time(secs):
    mins, secs = divmod(secs, 60)
    hours, mins = divmod(mins, 60)
    return '%02d:%02d' % (mins, secs)

get_status = subprocess.check_output("cmus-remote -Q | grep status | cut -c 8-", stdin=None, stderr=None, shell=True).decode("utf-8")
get_artist = subprocess.check_output("cmus-remote -Q | grep artist | cut -c 12-", stdin=None, stderr=None, shell=True).decode("utf-8")
get_song = subprocess.check_output("cmus-remote -Q | grep title | cut -c 11-", stdin=None, stderr=None, shell=True).decode("utf-8")
get_duration = int(subprocess.check_output("cmus-remote -Q | grep duration | cut -c 10-", stdin=None, stderr=None, shell=True).decode("utf-8"))
get_position = int(subprocess.check_output("cmus-remote -Q | grep position | cut -c 10-", stdin=None, stderr=None, shell=True).decode("utf-8"))



if get_status == "":
    stat = "Nothing playing..."
else:
    stat = (get_status)

if get_artist == "":
    artist = "Artist: No info..."
else:
    artist = ("Artist: "+get_artist)

if get_song == "":
    song = "Title: No info..."
else:
    song = ("Title: "+get_song)



print(stat.replace('\n', ""))
print(artist.replace('\n', ""))
print(song.replace('\n', ""))
print(readable_time(get_position),"/", (readable_time(get_duration)))
