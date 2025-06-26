# 🎷 Spotify Playback Data - Domain Documentation

This document outlines the schema and field-level metadata used for analyzing Spotify playback sessions. The dataset helps derive insights about user behavior, track popularity, platform usage, and engagement metrics.

---

## 🆔 `spotify_track_uri`

* **Description**: A unique identifier for each track in Spotify’s catalog.
* **Format**: `spotify:track:<base-62 string>`
* **Example**: `spotify:track:3n3Ppam7vgaVa1iaRUc9Lp`
* **Purpose**: Enables referencing tracks and linking them to their metadata.

---

## 🕒 `ts` (Timestamp)

* **Description**: The exact time when the track stopped playing.
* **Format**: ISO 8601 (e.g., `2024-02-07T14:30:45Z`)
* **Purpose**: Useful for session analysis, identifying listening times and durations.

---

## 💻 `platform`

* **Description**: The type of device or app used to stream the track.
* **Possible Values**:

  * `desktop` (Windows/Mac App)
  * `mobile` (iOS/Android App)
  * `web` (Web Player)
  * `smart_speaker` (e.g., Amazon Echo)
* **Purpose**: Understands user distribution across platforms.

---

## ⏱️ `ms_played`

* **Description**: Milliseconds the track was played before stopping.
* **Format**: Integer (e.g., `215000`)
* **Purpose**: Core metric for engagement, royalties calculation, and drop-off analysis.

---

## 🎵 `track_name`

* **Description**: The name of the track played.
* **Example**: "Shape of You"
* **Purpose**: Identifies most played tracks.

---

## 👨‍🎤 `artist_name`

* **Description**: The name of the artist.
* **Example**: "Ed Sheeran"
* **Purpose**: Helps rank top artists and identify user preferences.

---

## 📍 `album_name`

* **Description**: The album the track belongs to.
* **Example**: "÷ (Divide)"
* **Purpose**: Allows album-level listening trend analysis.

---

## ▶️ `reason_start`

* **Description**: Reason for track playback initiation.
* **Possible Values**:

  * `trackdone` – Previous track ended
  * `clickrow` – User manually clicked
  * `backbtn` – User pressed back
  * `fwdbtn` – User pressed next
  * `playbtn` – User hit play
  * `autoplay` – Automatically started by Spotify
* **Purpose**: Analyzes how and why tracks are being initiated.

---

## ⏹️ `reason_end`

* **Description**: Reason for stopping the track.
* **Possible Values**:

  * `trackdone` – Track finished
  * `endplay` – Paused or stopped
  * `fwdbtn` – Skipped forward
  * `backbtn` – Went to previous track
  * `logout` – Session ended
* **Purpose**: Determines why users stop listening, helping with churn/retention analysis.

---

## 🔀 `shuffle`

* **Description**: Indicates if shuffle mode was enabled.
* **Possible Values**:

  * `TRUE` – Shuffle ON
  * `FALSE` – Shuffle OFF
* **Purpose**: Analyzes user preference for randomized listening.

---

## ⏭️ `skipped`

* **Description**: Indicates whether the song was skipped.
* **Possible Values**:

  * `TRUE` – User skipped the track
  * `FALSE` – Track played normally
* **Purpose**: Key for measuring user interest and track quality.

---

## 📊 Usage

This schema is intended for data cleaning, exploratory analysis, and modeling tasks in Spotify usage analysis projects. Fields here are essential for identifying patterns in user behavior and track engagement.

---
