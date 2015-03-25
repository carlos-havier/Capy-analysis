README.TXT
----------

This is the log data corresponding to the Capy CAPTCHA analysis, to be published in IEEE Internet computing, with the article name "Image recomposition HIPs: using JPEG to measure image continuity and break Capy and other puzzle CAPTCHAs".

As described in the article, this log comprises:

- 2000 initial experiments (200 x 10) using different JPEG quality settings
- 1000 experiments at maximum JPEG quality (100)


Files:

- log.txt : original log
- challenges_and_answers.zip[1] : original PNG files containing the challenges, and computed answers to same challenges


log.txt
-------

Log format:

The log file is comma-separated. The fields are:

- name of the challenge image (to be found in challenges_and_answers.zip[1])
  note that the computed solution to each challenge has the name <challenge_name>_answer.PNG
- correct solution (or not) as returned by the Capy server
- relative displacement coordinate of the computed solution, from where the puzzle piece is first showed, in x-displacement and y-displacement
- string sent as answer to the Capy server, with:
  - original coordinate (0, 8e)
  - final coordinat of the solution
  coordinates are separated using the character 'x'
- name of the computed solution file (to be found in challenges_and_answers.zip[1])
- type of solver (indicates the quality setting for the JPEG)
- optional parameters (deprecated)
- seconds to download challenge
- seconds to solve challenge

Example:

* log line : CHALLENGE_39QvTXTrczHt98MlLLe0TFt5UoD4Kp.png, True, (110, -180), 3ex2qx, 0x8ex3ex2qx, CHALLENGE_39QvTXTrczHt98MlLLe0TFt5UoD4Kp_answer<NUM>.png, jpeg-size-solver-q-10, , [], 3.9509999752, 4.43799996376

* meaning of fields:
- CHALLENGE_39QvTXTrczHt98MlLLe0TFt5UoD4Kp.png : file with the challenge images
- True : challenge was correctly solved
- (110, -180) : relative position of the puzzle piece, from its starting position, for the computed solution
- 3ex2qx : position of the puzzle piece, for the computed solution, in base 32 (coordinates separated by 'x')
- 0x8ex3ex2qx : movement log sent to Capy (start + end position)
- CHALLENGE_39QvTXTrczHt98MlLLe0TFt5UoD4Kp_answer<NUM>.png : name of image containing solved challenge
- jpeg-size-solver-q-10 : type of JPEG solver used, in this case, with q = 10 (q : "quality")
- [] : deprecated
- 3.9509999752 : seconds to download challenge
- 4.43799996376 : seconds to solve challenge (on a regular Core-i3 desktop PC)


challenges_and_answers.zip
--------------------------

[1] : Due to GitHub size restrictions, this file has been divided in 100Mb parts.



