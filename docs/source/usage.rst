=====
Usage
=====

To run StimVis first navigate to the stimvis directory and then run the tms_stimulation.py file at the command line::


    $ python3 ./tms_stimulation.py

You will be asked to specify 4 input files and the output directory:

1. A file with tracts to analyse in the trk format

Example: ./Example_data/tracts.trk

2. A T1fs_conform image generated during head meshing procedure

Example: ./Example_data/T1fs_conform.nii.gz

3. A file with an FA map

Example: ./Example_data/dti_fa.nii

4. A volume conductor model generated during head meshing procedure

Example: ./Example_data/subject.msh

And finally, the output directory that will contain the resulting files with the TMS-induced effects

Example: /Example_data/Output

Once all input data is co-registered to each other (please, be patient as this may take a while) an interactive scene will open to 
visualize in 3D the tractography streamlines superimposed on T1-weighted images. By clicking at a particular location within a 
horizontal plane you can select the position of the stimulating coil and then press the big red button to start the calculations. 
As soon as the calculations are finished the total TMS effect will be shown over the streamlines in a color-coded manner. Also 
the calculated effects will be saved in a text file 

output_directory/stimulation_at_pos_<selected coil position>/subject_effective_field.txt 

via pickle.dump() in a form of a numpy array.

.. autofunction:: stimvis.tms_stimulation.change_TMS_effects
