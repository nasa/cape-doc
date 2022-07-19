
.. _pycart-json-PBS:

------------------
PBS Script Options
------------------

The "PBS" section of :file:`pyCart.json` controls settings for PBS scripts when
Cart3D runs are submitted as PBS jobs to a high-performance computing
environment.  Regardless of whether or not the user intends to submit PBS jobs,
pyCart creates scripts called :file:`run_cart3d.pbs` or
:file:`run_cart3d.01.pbs`, :file:`run_cart3d.02.pbs`, etc.  At the top of these
files is a collection of PBS directives, which will be ignored if the script is
launched locally.

To run such a script locally without submitting it, call it with the appropriate
shell.

    .. code-block:: bash
    
        $ bash run_cart3d.pbs
        
If the job is to be submitted, simply submit it.  A special script called
`pqsub` is recommended over the usual `qsub` because it also creates a file
:file:`jobID.dat` that saves the PBS job number

    .. code-block:: bash
    
        $ pqsub run_cart3d.pbs

The full description of the PBS section can be found in the corresponding
:ref:`Cape PBS section <cape-json-PBS>`.

