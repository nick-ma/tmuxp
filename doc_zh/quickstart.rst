.. _quickstart:

==========
快速启动
==========

安装
------------

确保你已经安装了最新版的tmux **>= 1.8** 和python **>= 2.6**。 对于Ubuntu 12.04/12.10/13.04 的用户来说，你可以从 `https://launchpad.net/ubuntu/+source/tmux <https://launchpad.net/ubuntu/+source/tmux>`_ 下载tmux 1.8，然后用dpkg来安装。

.. code-block:: bash

    $ pip install tmuxp

用如下命令将tmux升级到最新版:

.. code-block:: bash

    $ pip install tmuxp -U

然后安装 :ref:`bash_completion`.

命令行
-----

.. seealso:: :ref:`examples`, :ref:`cli`, :ref:`bash_completion`.

tmuxp通过加载JSON或YAML格式的配置文件来启动工作区／会话。

配置文件可以放在 ``$HOME/.tmuxp`` 或者放在项目目录下面，并以 ``.tmuxp.py``, ``.tmuxp.json`` 或 ``.tmuxp.yaml``来命名。

配置文件必需包含如下内容:

1. ``session_name``
2. ``windows`` 列表
3. 每个 ``windows`` 里面的 ``panes`` 列表。

新建一个文件, ``~/.tmuxp/example.yaml``:

.. literalinclude:: ../examples/2-pane-vertical.yaml
    :language: yaml

.. code-block:: bash

    $ tmuxp load example.yaml

以上命令创建了一个新的会话。

一次性加载多个会话:

.. code-block:: bash

    $ tmuxp load example.yaml anothersession.yaml

如果当前已经在一个会话中，tmuxp会提供一个 ``switch-client`` 选项供你切换到新加载进来的这个会话。

你还可以 `Import`_ 配置信息 `teamocil`_ 和 `tmuxinator`_.

.. _Import: http://tmuxp.readthedocs.io/en/latest/cli.html#import
.. _tmuxinator: https://github.com/aziz/tmuxinator
.. _teamocil: https://github.com/remiprev/teamocil



Pythonics
---------

.. seealso::
    :ref:`libtmux python API documentation <libtmux:api>` and :ref:`developing`,
    :ref:`internals`.


ORM - `Object Relational Mapper`_

AL - `Abstraction Layer`_

.. _Abstraction Layer: http://en.wikipedia.org/wiki/Abstraction_layer
.. _Object Relational Mapper: http://en.wikipedia.org/wiki/Object-relational_mapping

python 抽象层
""""""""""""""""""""""""

======================================== =================================
:ref:`tmuxp python api <libtmux:api>`    :term:`tmux(1)` equivalent
======================================== =================================
:meth:`libtmux.Server.new_session`       ``$ tmux new-session``
:meth:`libtmux.Server.list_sessions`     ``$ tmux list-sessions``
:meth:`libtmux.Session.list_windows`     ``$ tmux list-windows``
:meth:`libtmux.Session.new_window`       ``$ tmux new-window``
:meth:`libtmux.Window.list_panes`        ``$ tmux list-panes``
:meth:`libtmux.Window.split_window`      ``$ tmux split-window``
:meth:`libtmux.Pane.send_keys`           ``$ tmux send-keys``
======================================== =================================
