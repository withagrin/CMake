CUDA_ARCHITECTURES
------------------

List of architectures to generate device code for.

An architecture can be suffixed by either ``-real`` or ``-virtual`` to specify
the kind of architecture to generate code for.
If no suffix is given then code is generated for both real and virtual
architectures.

This property is initialized by the value of the :variable:`CMAKE_CUDA_ARCHITECTURES`
variable if it is set when a target is created.

The ``CUDA_ARCHITECTURES`` target property must be set to a non-empty value on targets
that compile CUDA sources, or it is an error.  See policy :policy:`CMP0104`.

Examples
^^^^^^^^

.. code-block:: cmake

  set_property(TARGET tgt PROPERTY CUDA_ARCHITECTURES 35 50 72)

Generates code for real and virtual architectures ``30``, ``50`` and ``72``.

.. code-block:: cmake

  set_property(TARGET tgt PROPERTY CUDA_ARCHITECTURES 70-real 72-virtual)

Generates code for real architecture ``70`` and virtual architecture ``72``.