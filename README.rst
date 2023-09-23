


.. code-block:: python

   import pyecharts.options as opts
   from pyecharts_extras.date_time import TimeYAxisDateXAxis, DateAxisOpts, TimeAxisOpts
   from datetime import datetime
   
   data = [
      datetime(2020,9,1,3,11,11),
      ...
   ]
   
   data2 = [
       datetime(2020,9,1,1,11,11),
       ...
   ]
   all_data = data1 + data2
   all_dates = sorted(list(set([str(d.date()) for d in all_data])))
   chart = TimeYAxisDateXAxis(init_opts=opts.InitOpts(height="1000px"))
   chart.set_global_opts(
            xaxis_opts=DateAxisOpts(axis_data=all_dates),
            yaxis_opts=TimeAxisOpts(),
            tooltip_opts=opts.TooltipOpts(is_show=False))   
   chart.add_data('A', data, symbol_size=10)
   chart.add_data('B', data2, symbol_size=20)
   chart.render_notebook()


.. image:: https://user-images.githubusercontent.com/4280312/92998181-4b4f6e00-f510-11ea-9b0a-963a83f64e04.png


2. ChoroplethMap
----------------

.. image:: https://user-images.githubusercontent.com/4280312/61274388-a0281500-a7a3-11e9-9501-27e8a1659bd0.png



.. code-block:: bash

    $ git clone https://github.com/pyecharts/pyecharts-extras.git
    $ cd pyecharts-extras
    $ python setup.py install
    $ pip install pyecharts-extras
