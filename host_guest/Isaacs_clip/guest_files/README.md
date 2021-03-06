# Guests for the SAMPL7 TrimerTrip Challenge

Provided are the guests for this challenge in PDB, Tripos MOL2 and SDF file format. The guests are codenamed from `g1` to `g15`.


## What's here

- `trimertrip_guest_smiles.txt` : isomeric SMILES strings and ids/codenames for all of the guests. Semicolon-delimited. Guests are not numbered consecutively due to updates from an earlier April version of this file.
- `input_maker.ipynb`: The jupyter notebook used to generate the PDB, MOL2 and SDF files for each guest using OpenEye toolkits and the SMILES strings and codenames found in `trimertrip_guest_smiles.txt`. For guest `g11` a random stereoisomer was chosen. The experiment was done on a racemic mix but because the host is achiral, the chirality of the guest is unimportant for binding.
- `SAMPL7.cdx` Chemdraw of the guests _and_ TrimerTrip host provided by Isaacs on May 14, 2019 (updated from an earlier file from April). Note, the jpg file in the images folder one directory above was generated by Mobley from this Chemdraw file. This Chemdraw file is the same as the one found in the `host_files` folder one directory above.
- `g11`: The files for this guest were missing coordinates and were corrected and added on 9/6/19.
