.. highlight:: bash

.. _batchsysteminterface:

The batch system interface
==========================

The batch system interface is used by Toil to abstract over different ways of running
batches of jobs, for example Slurm, GridEngine, Mesos, Parasol and a single node. The
:class:`toil.batchSystems.abstractBatchSystem.AbstractBatchSystem` API is implemented to
run jobs using a given job management system, e.g. Mesos.

Environmental variables allow passing of scheduler specific parameters.

For SLURM::

    export TOIL_SLURM_ARGS="-t 1:00:00 -q fatq"

For TORQUE::

    export TOIL_TORQUE_ARGS="-l walltime=1:00:00 -q fatq"

For GridEngine (SGE, UGE), there is an additional environmental variable to define the
`parallel environment <https://blogs.oracle.com/templedf/entry/configuring_a_new_parallel_environment>`_
for running multicore jobs::

    export TOIL_GRIDENGINE_PE='smp'
    export TOIL_GRIDENGINE_ARGS='-q batch.q'

.. autoclass:: toil.batchSystems.abstractBatchSystem::AbstractBatchSystem
   :members:
