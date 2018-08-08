## 下载爬虫图片
通过修改topic, 可在多台服务器部署，做到分布式爬取

1. 配置文件解读

    kafka_host: kafka地址，例如：kafka1.jujin8.com:9092,kafka2.jujin8.com:9092,kafka3.jujin8.com:9092
    kafka_consumer_group: kafka的consumer_group
    kafka_consumer_id: kafka的consumer_id

    download_img_topic: 下载图片的kafka的topic
    download_file_topic: 下载文件的kafka的topic

    redis_host: redis的地址
    redis_port: redis端口号

    images_path: 图片存储路径
    thumb_folder: 缩略图下载的文件夹名称，路径为images_path下
    thumb_width: 生成的缩略图的宽度
    images_url_prefix: 图片链接前缀

    console=是否开启命令行输出

    download_time_out: 下载超时时间
    
2. 启动

    python main.py -a image -c True
    
    参数：
    
    * a: image | file, 下载图片或者文件   
    * c: True | False | 不填， 是否控制台输出，不填则看.env文件的配置
        
3. 依赖

        mkdir logs
        pip install pillow
        pip install pykafka
        pip install python-dotenv
        pip install redis