# rasa_chatbot
A Chinese task oriented chatbot in  IVR(Interactive Voice Response) domain(电信ivr领域， 中文)， Implement by rasa nlu and rasa core. This is a demo with toy dataset.

### requirements:
- python3
- [rasa_nlu_chi](https://github.com/crownpku/rasa_nlu_chi)
- [rasa_core](https://github.com/RasaHQ/rasa_core)
- sklearn
- mitie [(you can install follow here)](https://nlu.rasa.ai/installation.html#section-backends)

### dir tree
```
rasa_chatbot/
├── data
│   ├── mobile_nlu_data.json  # rasa nlu train data
│   ├── mobile_story.md       # rasa core train data
│   └── total_word_feature_extractor.dat  # mitie word vector feature
├── __init__.py               # init file
├── httpserver.py             # rasa nlu httpserver
├── bot.py                    # ivr bot main script.
├── mobile_domain.yml         # rasa core domain file
├── mobile_nlu_model_config.json  # rasa nlu config file
├── models                    # directory to save trained models
└── README.md                 # readme file

```

### train nlu model
```bash
python bot.py train-nlu
```

### train dialogue
```bash
python bot.py train-dialogue
```

### test
Run command below:
```bash
python bot.py run
```
Example1:
```
Bot loaded. Type a message and press enter : 
YOU：你是谁
BOT：您好!，我是机器人小热，很高兴为您服务。
YOU：我想看一下消费情况
BOT：您想查询哪个月的消费？
YOU：十月份的
BOT：好，请稍等
BOT：您好，您十月份共消费二十八元。
YOU：好谢谢
BOT：您开心我就开心
BOT：您还想干什么
YOU：没什么了
BOT：Bye， 下次再见

```
Example2:
```
Bot loaded. Type a message and press enter : 
YOU：给我看看我上月用了多少话费
BOT：好，请稍等
BOT：您好，您上月共消费二十八元。
BOT：您还想干什么

```