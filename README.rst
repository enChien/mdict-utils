=========
Pyinstaller
=========
安裝 python 環境
    https://www.python.org/downloads/

安裝 pyinstaller::
    
    pip install pyinstaller

修正 __main__.py import 路徑為絕對路徑::

    from mdict_utils import about
    from mdict_utils import reader
    from mdict_utils.writer import pack, pack_mdd_file, etc.
    from mdict_utils.utils import ElapsedTimer


切換到 mdict-utils 目錄下，開啟 power shell 並執行::
    
    pyinstaller.exe -F -n runme .\__main__.py

mdic_utils 目錄下會多出 build, dist 目錄，打包好的 exe 位於 dist 目錄下。使用語法範例::

    .\runme.exe -x ./test.mdx -d ./

==========
MDict Tool
==========

MDict pack/unpack tool

.. NOTE::

    Support Reading with MDict Version 3.0

    Support Reading and Writing with MDict Version 2.0

    All files must be UTF-8 encoding, include HTML and TXT


Install
=======
::

    pip install mdict-utils

Usage
=====
Meta information::

    mdict -m dict.mdx

All key list::

    mdict -k dict.mdx

Query key::

    mdict -q <word> dict.mdx

.. note::

    只用于测试词典打包是否正确。

Unpack
------
Unpack MDX::

    mdict -x dict.mdx -d ./mdx

Unpack MDX/MDD and split into 5 files::

    mdict -x dict.mdx -d ./mdx --split-n 5

Unpack MDX/MDD and split into a...z files::

    mdict -x dict.mdx -d ./mdx --split-az

Unpack MDD::

    mdict -x dict.mdd -d ./mdd

Unpack MDX/MDD to sqlite3 DB::

    mdict -x dict.mdx --exdb
    mdict -x dict.mdd --exdb

Unpack MDX/MDD to sqlite3 DB with zip compress::

    mdict -x dict.mdx --exdb-zip

Pack
----
Pack MDX::

    mdict --title title.html --description description.html -a dict.txt dict.mdx

Pack MDX with many TXT files::

    mdict --title title.html --description description.html -a dict.part1.txt -a dict.part2.txt dict.mdx

or::

    mdict --title title.html --description description.html -a txt_dir dict.mdx

Pack MDD::

    mdict --title title.html --description description.html -a mdd_dir dict.mdd

Other
-----
Convert TXT to sqlite3 DB::

    mdict --txt-db dict.txt

Convert sqlite3 DB to TXT::

    mdict --db-txt dict.db


Reference
=========

+   https://bitbucket.org/xwang/mdict-analysis
+   https://github.com/zhansliu/writemdict

Donate 捐赠
=============

.. image:: alipay_pay.jpg
    :width: 45%
.. image:: wx_pay.png
    :width: 45%
