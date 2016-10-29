.. _api:

=============
API 参考
=============

.. seealso::
    通过python调用API来控制tmux，请参考 :ref:`libtmux's API <libtmux:api>` and :ref:`Quickstart
    <libtmux:quickstart>` 。

.. module:: tmuxp

内部
---------

.. automethod:: tmuxp.util.run_before_script


配置
-------------

查找
"""""""

.. automethod:: tmuxp.config.is_config_file
.. automethod:: tmuxp.config.in_dir
.. automethod:: tmuxp.config.in_cwd

导入与导出
"""""""""""""""""

.. automethod:: tmuxp.config.validate_schema

.. automethod:: tmuxp.config.expandshell

.. automethod:: tmuxp.config.expand

.. automethod:: tmuxp.config.inline

.. automethod:: tmuxp.config.trickle

.. automethod:: tmuxp.config.import_teamocil

.. automethod:: tmuxp.config.import_tmuxinator

工作区构建器
-----------------

.. autoclass:: tmuxp.WorkspaceBuilder
   :members:

异常
----------

.. autoexception:: tmuxp.exc.EmptyConfigException

.. autoexception:: tmuxp.exc.ConfigError

.. autoexception:: tmuxp.exc.BeforeLoadScriptError

.. autoexception:: tmuxp.exc.BeforeLoadScriptNotExists
