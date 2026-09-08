blueticks Solutions — assets folder
===================================

Three of the four files here are PLACEHOLDERS. The site works and looks
finished without touching them, but replace them when the real video is ready.


1. hero-video.mp4          ** PLACEHOLDER — replace **
------------------------------------------------------
The full-width background clip on desktop (screens 900px and wider).

  Format   : MP4 (H.264), 16:9, 1920x1080
  Length   : 8-12 seconds, must loop cleanly
  Audio    : none (the page plays it muted anyway — strip the audio track
             to save file size)
  Filming  : shot at 60fps, because the page plays it back at 0.6x speed
             for the slow-motion look
  Size     : keep it under about 6 MB or the hero takes too long to appear

  Prompt used to generate it:

    "A warm, slow-motion, cinematic close-up: a barista's hands pouring
     coffee into a white cup on a wooden counter, steam rising gently,
     soft golden-hour window light, shallow depth of field, muted
     background. Transitions smoothly into a close-up of a smartphone
     screen scrolling vertical video content (reels), warm ambient
     lighting reflecting off the screen. No visible faces, no on-screen
     text, no logos. Loopable, 8-12 seconds, shot at 60fps for smooth
     slow-motion playback. Muted, no dialogue."


2. hero-video-vertical.mp4  ** PLACEHOLDER — replace **
-------------------------------------------------------
The same clip, cropped to 9:16 (1080x1920). This is what opens in the
popup when someone on a phone taps "Tap to watch". Phones never download
the big landscape file — that's deliberate, it saves their data.


3. hero-poster.jpg          (working placeholder — replace when you can)
------------------------------------------------------------------------
The still image behind the hero text. Right now it's a warm gradient that
matches the brand colours, so the page looks right out of the box.

Replace it with the FIRST FRAME of hero-video.mp4, exported at 1920x1080
JPG, quality around 80. That way the video fades in from the still with no
visible jump.

This image is doing a lot of work — it's what mobile visitors see instead
of the video, and what anyone with "reduce motion" turned on sees too.


4. favicon.svg              (final — no need to change)
--------------------------------------------------------
The little blue-tick icon in the browser tab.


If a video file is missing or broken
------------------------------------
Nothing breaks. The page checks, and quietly falls back to the poster
image. So you can upload the site today and drop the real videos in later
by just overwriting these two files — no code changes needed.
