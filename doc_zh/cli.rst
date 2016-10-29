.. _cli:
.. _commands:

======================
命令行参数
======================

.. _completion:

自动补全
----------

In zsh (``~/.zshrc``) or bash (``~/.bashrc``):

.. code-block:: sh

    eval "$(_TMUXP_COMPLETE=source tmuxp)"

.. _cli_freeze:

冻结会话
---------------

::

    tmuxp freeze <session_name>

你可以通过冻结操作来保存你的tmux会话状态信息。

tmuxp提供了2种保存的格式，分别是 ``.json`` 和 ``.yaml``。

.. _cli_load:

加载会话
------------

::

    # 含有 .tmuxp.{yaml,yml,json} 文件的路径
    tmuxp load .
    tmuxp load ../
    tmuxp load path/to/folder/
    tmuxp load /path/to/folder/

    # 文件名，假设 $HOME/.tmuxp/myconfig.yaml
    tmuxp load myconfig

    # json/yaml 文件的完整路径。
    tmuxp load ./myfile.yaml
    tmuxp load /abs/path/to/myfile.yaml
    tmuxp load ~/myfile.yaml

通过绝对路径加载。
Files also may be loaded by absolute path.

.. code-block:: bash

    $ tmuxp load <filename>

加载当前工作路径下的文件名为 ``.tmuxp.yaml`` 或 ``.tmuxp.json`` 的文件:

.. code-block:: bash

    $ tmuxp load .

可以一次性加载多个会话。第一个将创建回话，最后一个如果命令行里没有 ``-d`` 选项的话，则是挂载。

.. code-block:: bash

    $ tmuxp load <filename1> <filename2> ...

.. _cli_import:

导入
------

.. _import_teamocil:

从 teamocil 导入
~~~~~~~~~~~~~~~

::

    tmuxp import tmuxinator /path/to/file.{json,yaml}

.. _import_tmuxinator:

从 tmuxinator 导入
~~~~~~~~~~~~~~~~~

::

    tmuxp import tmuxinator /path/to/file.{json,yaml}

.. _convert_config:

YAML与JSON格式互相转换
-----------------------------

::

    tmuxp convert /path/to/file.{json,yaml}

tmuxp 会自动提示 ``.yaml`` 转 ``.json`` 还是
``.json`` 转  ``.yaml``。
