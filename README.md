# Code for 'Musical Pattern Recognition in Spiking Neural Networks'

This repository contains the source code for my final-year project in my BEng
degree, 'Musical Pattern Recognition in Spiking Neural Networks'. The title of
the project should hopefully be self-descriptive as to the purpose of the
project.

As seems to be the case with pretty much all final-year projects, only a small
portion of what was originally intended was actually achieved. This code
implements the first layer of the model proposed in the report: a layer of
spiking neurons which can differentiate between individual notes in a series of
simple monophonic test audio sequences.

## Files

* `test_inputs` contains a number of test sequences in `.wav` files, generated
  by `gen_audio_spikes.py`. (`comptine*.wav` is a test sequence based on the
  first few chords of Yann Tiersen's 'Comptine d'un autre été', generated by a
  script not supplied.) The `.pickle` files are spike-coded representations of
  these sequences in `.pickle` files, generated by `gen_audio_spikes.py`.
* `stdp_sounds.py` is the main simulation script. See `params/*_cmdline.txt` for
  examples of good parameters to run it with for each test sequence. The
  simulation script will record the parameters used in `params`, save results
  in `results`, and save figures generated in `figures`.
* `modules` contains Python modules used for the simulation.
* `input-layer1e-weights.pickle` is a cache of the random initial synaptic
  weights used in the simulation, for repeatability.
* `prepare_movie_with_sound.sh` uses `write_movie.py` and the results of a
  single simulation (as stored in `results/monitors_<test sequence
  name>.pickle`) to generate an animation showing the input spikes, neuron
  membrane potentials and weight changes over time, then combine it with the
  corresponding audio track using `ffmpeg`. Examples of these animations are
  included in `results`.
