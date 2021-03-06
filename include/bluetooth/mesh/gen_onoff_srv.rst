.. _bt_mesh_onoff_srv_readme:

Generic OnOff Server
####################

The Generic OnOff Server represents a single controllable On/Off value.

States
=======

This model has the following states:

**Generic OnOff:** ``boolean``

Generic boolean state representing an On/Off state.
The user is expected to hold the state memory and provide access to the state through the :cpp:type:`bt_mesh_onoff_srv_handlers` handler structure.

Changes to the Generic OnOff state may include transition parameters.
When transitioning to a new OnOff state, the state should be `on` during the entire transition, regardless of target state.
This ensures that any bound non-binary states can have non-0 values during the transition.

Any requests to read out the current OnOff state while in a transition should report the current OnOff value being `on`.

The ``remaining_time`` parameter should be reported in milliseconds, including delay.
If the transition parameters includes a delay, the state shall remain unchanged until the delay expires.

Extended models
================

None.

Persistent storage
===================

None.

API documentation
==================

| Header file: :file:`include/bluetooth/mesh/gen_onoff_srv.h`
| Source file: :file:`subsys/bluetooth/mesh/gen_onoff_srv.c`

.. doxygengroup:: bt_mesh_onoff_srv
   :project: nrf
   :members:
