docker run --name redis_db -p 6379:6379 redis
docker exec -it redis_db redis-cli


docker run -p 6379:6379 -d redis:5

python3 manage.py shell
import channels.layers
channel_layer = channels.layers.get_channel_layer()
from asgiref.sync import async_to_sync
async_to_sync(channel_layer.send)('test_channel', {'type': 'hello'})
async_to_sync(channel_layer.receive)('test_channel')
{'type': 'hello'}

Type Control-D to exit the Django shell