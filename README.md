# assignment19.2


thrift -gen py /path/to/hbase/source/hbase-VERSION/src/main/resources/org/apache/hadoop/hbase/thrift/Hbase.thrift

export PYTHONPATH=$PYTHONPATH:/<path to gen-py>

$hbase thrift start
save below python code int table.py
from thrift.transport.TSocket import TSocket
from thrift.transport.TTransport import TBufferedTransport
from thrift.protocol import TBinaryProtocol
from hbase import Hbase 
 
transport = TBufferedTransport(TSocket('localhost', 9090))
transport.open()
protocol = TBinaryProtocol.TBinaryProtocol(transport)
client = Hbase.Client(protocol)
print(client.getTableNames())


1.for key, data in index.scan(filter="RowFilter(=,'substring:AUS')"):
    print key, data



