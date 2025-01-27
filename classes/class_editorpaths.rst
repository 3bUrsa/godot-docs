:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in Godot's source tree.
.. DO NOT EDIT THIS FILE, but the EditorPaths.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_EditorPaths:

EditorPaths
===========

**Inherits:** :ref:`Object<class_Object>`

Editor-only singleton that returns paths to various OS-specific data folders and files.

Description
-----------

This editor-only singleton returns OS-specific paths to various data folders and files. It can be used in editor plugins to ensure files are saved in the correct location on each operating system.

**Note:** This singleton is not accessible in exported projects. Attempting to access it in an exported project will result in a script error as the singleton won't be declared. To prevent script errors in exported projects, use :ref:`Engine.has_singleton<class_Engine_method_has_singleton>` to check whether the singleton is available before using it.

**Note:** Godot complies with the `XDG Base Directory Specification <https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html>`__ on *all* platforms. You can override environment variables following the specification to change the editor and project data paths.

Tutorials
---------

- `File paths in Godot projects <https://docs.godotengine.org/en/latest/tutorials/io/data_paths.html>`__

Methods
-------

+-----------------------------+------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_cache_dir<class_EditorPaths_method_get_cache_dir>` **(** **)** |const|                     |
+-----------------------------+------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_config_dir<class_EditorPaths_method_get_config_dir>` **(** **)** |const|                   |
+-----------------------------+------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_data_dir<class_EditorPaths_method_get_data_dir>` **(** **)** |const|                       |
+-----------------------------+------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>` | :ref:`get_self_contained_file<class_EditorPaths_method_get_self_contained_file>` **(** **)** |const| |
+-----------------------------+------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`     | :ref:`is_self_contained<class_EditorPaths_method_is_self_contained>` **(** **)** |const|             |
+-----------------------------+------------------------------------------------------------------------------------------------------+

Method Descriptions
-------------------

.. _class_EditorPaths_method_get_cache_dir:

- :ref:`String<class_String>` **get_cache_dir** **(** **)** |const|

Returns the absolute path to the user's cache folder. This folder should be used for temporary data that can be removed safely whenever the editor is closed (such as generated resource thumbnails).

**Default paths per platform:**

::

    - Windows: %LOCALAPPDATA%\Godot\
    - macOS: ~/Library/Caches/Godot/
    - Linux: ~/.cache/godot/

----

.. _class_EditorPaths_method_get_config_dir:

- :ref:`String<class_String>` **get_config_dir** **(** **)** |const|

Returns the absolute path to the user's configuration folder. This folder should be used for *persistent* user configuration files.

**Default paths per platform:**

::

    - Windows: %APPDATA%\Godot\                    (same as `get_data_dir()`)
    - macOS: ~/Library/Application Support/Godot/  (same as `get_data_dir()`)
    - Linux: ~/.config/godot/

----

.. _class_EditorPaths_method_get_data_dir:

- :ref:`String<class_String>` **get_data_dir** **(** **)** |const|

Returns the absolute path to the user's data folder. This folder should be used for *persistent* user data files such as installed export templates.

**Default paths per platform:**

::

    - Windows: %APPDATA%\Godot\                    (same as `get_config_dir()`)
    - macOS: ~/Library/Application Support/Godot/  (same as `get_config_dir()`)
    - Linux: ~/.local/share/godot/

----

.. _class_EditorPaths_method_get_self_contained_file:

- :ref:`String<class_String>` **get_self_contained_file** **(** **)** |const|

Returns the absolute path to the self-contained file that makes the current Godot editor instance be considered as self-contained. Returns an empty string if the current Godot editor instance isn't self-contained. See also :ref:`is_self_contained<class_EditorPaths_method_is_self_contained>`.

----

.. _class_EditorPaths_method_is_self_contained:

- :ref:`bool<class_bool>` **is_self_contained** **(** **)** |const|

Returns ``true`` if the editor is marked as self-contained, ``false`` otherwise. When self-contained mode is enabled, user configuration, data and cache files are saved in an ``editor_data/`` folder next to the editor binary. This makes portable usage easier and ensures the Godot editor minimizes file writes outside its own folder. Self-contained mode is not available for exported projects.

Self-contained mode can be enabled by creating a file named ``._sc_`` or ``_sc_`` in the same folder as the editor binary while the editor is not running. See also :ref:`get_self_contained_file<class_EditorPaths_method_get_self_contained_file>`.

**Note:** The Steam release of Godot uses self-contained mode by default.

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
.. |constructor| replace:: :abbr:`constructor (This method is used to construct a type.)`
.. |static| replace:: :abbr:`static (This method doesn't need an instance to be called, so it can be called directly using the class name.)`
.. |operator| replace:: :abbr:`operator (This method describes a valid operator to use with this type as left-hand operand.)`
