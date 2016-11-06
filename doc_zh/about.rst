.. module:: tmuxp

.. _about:

=====
关 于
=====

tmuxp是一个帮你管理tmux会话的工具。

tmuxp是基于tmux的对象关系映射技术构建的。 你可以像使用使用 `tmuxinator`_ 和 `teamocil`_ 一样
通过加载 YAML, JSON 和 :py:obj:`dict` 类型的配置文件来管理工作区。 

想马上体验tmuxp？ 请见： :ref:`quickstart` and :ref:`examples`.

如果对内部的武功感兴趣，或则也想参与进来，请参见：  :ref:`api` 和
:ref:`developing` 。

`BSD-licensed`_. 代码托管在 `github 
<http://github.com/tony/tmuxp>`_.

与 tmuxinator / teamocil 的区别
--------------------------------------

.. note::

    如果你正在使用 teamocil 或 tmuxinator，并且对他们之间的差异很清楚，
    请在github上  `edit this page`_ 。 
    
相同点
~~~~~~~~~~~~

**加载会话** 从配置文件中加载tmux会话

**YAML** 支持YAML格式

**单行命令／短命令的配置方式** 3个工具都支持短命令并且也支持在单行命令中使用简单的标记语言来配置面板。.

**坚实稳定** 截止到目前的2016年，这3个工具都很稳定，被良好的测试过以及在不同环境的适配。

缺失点
~~~~~~~

**版本支持** tmuxp 只支持 ``tmux >= 1.8`` 以上的版本。Teamocil和tmuxinator可能会支持更老一些的版本。

不同点
~~~~~~~~~~~

**编程语言** tmuxp使用Python。 teamocil和tmuxinator使用Ruby。

**建立工作区的过程** teamocil和tmuxinator通过直接处理shell指令来执行配置信息。tmuxp使用ORM来执行配置信息。 

新特性
-------------------

**CLI** tmuxp的CLI可以挂载或者杀掉会话。同时也命令行支持自动补全功能。详情请见： :ref:`commands`.

**导入配置** 可以从Teamocil或Tmuxinator导入配置 [1]_。 详情请见：:ref:`cli_import`.

**冻结会话** 支持将会话冻结到YAML和JSON格式的文件中。[1]_。 详情请见： :ref:`cli_freeze`.

**JSON格式配置文件** 支持JSON格式的配置文件，详情请见： :ref:`Examples` 。

**基于ORM的API** - 使用 tmux >= 1.8 版本的面板、窗口和会话的唯一ID，通过 
:class:`Server` ， :class:`Session`， :class:`Window`， :class:`Pane`
来创建出对象关系视图。详情请见： :ref:`Internals` 。

**配置文件的格式转换** ``$ tmuxp convert <filename>`` 可以将配置文件格式在YAML和JSON之间转换。

.. [1] 冻结和导入会话可以节省大量的时间。想做到这一点，还需要一些小技巧。经过细心配置的文件实在是不可替代的神器。

小技巧
------------

- 使用所有现存的tmux版本执行单元测试。确保tmux的会话，窗口和面板都能正确的使用。详情请见： :ref:`travis`.
- 在tmux的会话内部加载并切换到新的会话。
- 如果配置文件已经加载了，就恢复会话。
- 可以使用任何的前置命令。
- 加载放在任何位置的配置文件 ``$ tmuxp load /full/file/path.json``.
- 在当前目录下加载 ``.tmuxp.yaml`` 或 ``.tmuxp.json`` 配置文件，使用：``$ tmuxp load .``。
- ``$ tmuxp -2``, ``$ tmuxp -8`` for forcing term colors a la
  :term:`tmux(1)`.
- 当用socket时使用 ``$ tmuxp -L<socket-name>``, ``$ tmuxp -S<socket-path>`` ，当用配置文件时使用
  ``$ tmuxp -f<config-file>`` 。

更多详情
------------

.. include:: ../README.rst
    :start-after: ---------------

.. _attempt at 1.7 test: https://travis-ci.org/tony/tmuxp/jobs/12348263
.. _kaptan: https://github.com/emre/kaptan
.. _BSD-licensed: http://opensource.org/licenses/BSD-2-Clause
.. _tmuxinator: https://github.com/aziz/tmuxinator
.. _teamocil: https://github.com/remiprev/teamocil
.. _ERB: http://ruby-doc.org/stdlib-2.0.0/libdoc/erb/rdoc/ERB.html
.. _edit this page: https://github.com/tony/tmuxp/edit/master/doc/about.rst
