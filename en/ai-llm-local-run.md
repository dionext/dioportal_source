---
title: "AI. Local model run"
description: ""
keywords: ""
lang: "en"
permalink: "ai-llm-local-run"
aliases:
  - "ai-llm-local-run"
---


# AI. Local model run

## ollama

Активно испаользуется в интеграции Spring AI

[https://ollama.com](https://ollama.com)

[https://github.com/ollama/ollama](https://github.com/ollama/ollama)

[https://github.com/ollama/ollama/blob/main/README.md](https://github.com/ollama/ollama/blob/main/README.md)

список моделей [https://ollama.com/library](https://ollama.com/library)

ссылка на страницу с мультимодальной моделью:  
[https://ollama.com/library/llava](https://ollama.com/library/llava)

рекомендуют GUI [https://github.com/open-webui/open-webui](https://github.com/open-webui/open-webui)

ссылка на видео:  
https://youtu.be/J2pWl4UeSa4

ссылка на проект:  
https://github.com/ollama/ollama

#### Инсталляция Windows

одной командой для виндовс:

https://ollama.com/download/OllamaSetup.exe

установка веб интерфейса open-webui: источник https://github.com/open-webui/open-webui  
Запуск open-webui: перейти в папку open-webui/backend и запустить файл start\_windows.bat  
перейти в браузер и ввести localhost:8080  
https://docs.openwebui.com/getting-started/#alternative-installation-methods  
замечания:  
Во время первого входа попадете на страницу регистрации. Перейти на создание  
нового пользователя и ввести любые можно фейковые данные

У кого проблемы со свободным местом для ollama на диске С - нужно задать переменную окружения OLLAMA\_MODELS=путь\\до\\папки. Должно сработать и для другого диска. Туда будут сохранены все загруженные модели, которые и выедают место

OLLAMA\_MODELS=D:\\Soft\\AI\\ollama\\models  
Where are models stored?

* macOS: ~/.ollama/models
* Linux: /usr/share/ollama/.ollama/models
* Windows: C:\\Users\\%username%\\.ollama\\models

1. In the Environment Variables window, edit or create a new variable for your user account:
   * Variable Name: OLLAMA\_HOST
   * Variable Value: 0.0.0.0
2. Create a new variable for OLLAMA\_ORIGINS with value "\*"

Настройка для входа из сети

Ollama binds 127.0.0.1 port 11434 by default. Change the bind address with the OLLAMA\_HOST environment variable.

Ollama allows cross-origin requests from 127.0.0.1 and 0.0.0.0 by default. Additional origins can be configured with OLLAMA\_ORIGINS

OLLAMA\_HOST=0.0.0.0

тоже в виде комманды

OLLAMA\_HOST="0.0.0.0" ollama serve

Проверка

\[curl http://192.168.1.75:11434/api/generate -d '{ "model": "mistral", "prompt": "What is water made of?" }'\](../../../../dio\_documents/other/curl%20http:/192.168.1.75:11434/api/generate%20-d%20'{%20%22model%22:%20%22mistral%22,%20%22prompt%22:%20%22What%20is%20water%20made%20of?" }')

#### Инсталляция Linux

одной командой для линукс:

curl -fsSL https://ollama.com/install.sh | sh  
Where are models stored?

* Linux: /usr/share/ollama/.ollama/models

[https://translucentcomputing.github.io/kubert-assistant-lite/ollama.html https://github.com/ollama/ollama/blob/main/docs/linux.md](https://github.com/ollama/ollama/blob/main/docs/linux.md)

#### Инсталляция Docker

Вариант установки GUI с внедренной ollama: (через интерфейс работает, но апи не доступно -p 11434:11434 - не помогает)

docker run -d -p 3000:8080 -v ollama:/root/.ollama -v /mnt/ai/open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama

docker run -d --network=host -v ollama:/root/.ollama -v /mnt/ai/open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama

Вариант отдельной установки

docker run -d -v /mnt/ai/ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v /mnt/ai/open-webui-single:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main

(установить c помощью докер:  
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main)

docker run -d -p 3000:8080 -e OLLAMA\_BASE\_URL=https://example.com -v /mnt/ai/open-webui-single:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main

#### Инсталляция дополнительного?

установить visual build tools:

https://visualstudio.microsoft.com/visual-cpp-build-tools/

установить гит:

https://github.com/git-for-windows/git/releases/download/v2.44.0.windows.1/Git-2.44.0-64-bit.exe

установить python 3.11:

https://www.python.org/ftp/python/3.11.0/python-3.11.0-amd64.exe

установить node js:

https://nodejs.org/en

установить bun:

powershell -c "irm bun.sh/install.ps1|iex"

запустить в powershell установку open-webui:

git clone https://github.com/open-webui/open-webui.git  
cd open-webui/

# Copying required .env file

cp -RPp example.env .env

# Building Frontend Using Node

npm i  
npm run build

# Serving Frontend with the Backend

cd ./backend  
pip install -r requirements.txt -U

#### Комманды

pulling model:

ollama run llama3.1

ollama run llama3.2:3b  
List models on your computer

```
ollama list
```

List which models are currently loaded

```
ollama ps
```

## Other tools

[https://jan.ai/](https://jan.ai/) Chat with AI without privacy concerns Jan is an open source ChatGPT-alternative that runs 100% offline.

## Economy, efficiency calculations

[https://www.youtube.com/watch?v=XAPoBtIMhQY](https://www.youtube.com/watch?v=XAPoBtIMhQY) Экономика LLM: что надо и сколько стоит использование больших языковых моделей

• Renting a server is a high entry threshold

• Optimal if used 24/7 with approximately equal load

• Depends on your tasks

• It is not profitable to run "senior" models

• A hybrid option seems optimal

• Your own server gives the opportunity to run pre-trained models

[https://habr.com/ru/companies/beeline\_cloud/articles/821151/](https://habr.com/ru/companies/beeline_cloud/articles/821151/)

### Some advices about Hardware from Internet

[https://render.ru/ru/DigitalRazor/post/26204](https://render.ru/ru/DigitalRazor/post/26204)  
And AMD Threadripper Pro and Intel Xeon W processors cope much better with a huge array of data than AMD Ryzen and Intel Core. If we talk separately about the difference between Intel and AMD processors, their work with graphics processors is almost identical.  
Modern video accelerators provide much greater performance compared to the CPU. At the same time, video cards are usually equipped with a memory capacity in the range of 8 to 48 GB. This limits the ability to run some models on the GPU.  
The CPU uses system RAM. This allows you to work with larger models that cannot be loaded into video memory (VRAM). The main disadvantage is the low performance of the CPU compared to video accelerators. A powerful GPU can work with the same language model 10-100 times faster. There are libraries for inference that support a hybrid approach. This method uses the resources of both the CPU and GPU. For example, llama.cpp is a suitable solution for running models that do not fit in VRAM. This approach will provide a happy medium in performance between CPU and GPU-based calculations.  
RAM is usually an auxiliary element. Except when the CPU processes data. When using a GPU, RAM serves to facilitate the transfer of model data from storage to video memory. Therefore, the recommended RAM size should be equal to the video memory size, and preferably 1.5-2 times larger. Even if LLM is fully loaded into VRAM, it should be remembered that RAM must fit not only the model, but also the system swap file. However, after loading the model, the function of RAM is reduced to a minimum.

[https://habr.com/ru/companies/beeline\_cloud/articles/821151/](https://habr.com/ru/companies/beeline_cloud/articles/821151/)

You can host Lama on CPU, 70b eats about 30 GB (in RAM), some layers can be thrown into the video card, but in general the speed will be limited by the CPU. I made a choice in favor of the "server Chinese Zion" for 24 threads, 64 GB RAM. It works rather slowly, but if this is not critical - then in my opinion the best option for your money. Of course, there is no smell of any millions or even hundreds of thousands of rubles here. The size of the video frames is critical for speed. For performance, it is not critical. 4Gb will not help in any way (well, that is, they will help somehow, but it will still be very painful). 8Gb IMHO is a minimum for experiments without special expectations. LLama3 8B slightly quantized will fit into 8Gb. On 16Gb you can already load some number of 70B layers, so that the effect is clearly visible.  
Look at the messages of this bot https://huggingface.co/model-sizer-bot/activity/community , it takes different open llm models and calculates the minimum RAM requirements for their training and launch, depending on the type of quantization, for example for llama3-70b, unfortunately this model just barely fits into 64gb for 8bit quantization (it is even used for some finetuning) and 4bit (which already noticeably breaks the quality, by 3-5%) also does not fit into 32gb  
Working with llm is two directions - finetuning (training) and inference (use) and each of them has its own hardware requirements. For inference, RAM may be sufficient and the launch can be performed on the processor, since even 70b models on average hardware will give a speed of about 1 token per second, moreover, quantization is possible in this mode, when the network weights take up to 4 bits per weight instead of 16 bits on average (it can be less, but the quality drops significantly) and the speed in this case also increases. But for finetuning, quantization is almost always contraindicated, which means that the requirements for RAM are maximum. Also, the ability to place a training sample next to the model weights can increase the speed of operation many times, which is also critical. when choosing amd or intel video card, ready-made solutions will be limited to llama.cpp while with nvidia almost any code will work

Recommendation for cheap hardware for home llm - nvidia gtx 3060 12gb or 4060ti 16gb, these are very slow video cards from nvidia (the company did this on purpose) but with the lowest cost per gigabyte of vram. The processor and RAM should not be the most top-end, fast RAM is not needed, here you can save money. The disk should be the fastest for reading, any cheap ssd nvme pci-e will do, but then be prepared for frequent replacements, llm-ki are hundreds of gigabytes, especially if you often save pretrained when you are doing finetuning. .... After about 3-4 months of load, the rental costs will be equal to the purchase of hardware, and if there is an opportunity to sell it later, even taking into account the high depreciation, the benefit becomes even more noticeable. I thought above in the comment that for inference llama70b a machine for 300-350 thousand rubles would be enough (about 10-20 tokens per second, for batching 50 would be reasonable), we take the best service for gpu calculations vast ai - 4x16 gb will cost $ 360 per month, this 34 thousand rubles will allow you to work for more than six months (it is better to take interruptible there, by the way, such prices are rare there, more often 2 times more expensive).

[https://vc.ru/ai/881777-spravochnik-po-vyboru-gpu-dlya-raboty-s-bolshimi-yazykovymi-modelyami-llama](https://vc.ru/ai/881777-spravochnik-po-vyboru-gpu-dlya-raboty-s-bolshimi-yazykovymi-modelyami-llama)

RTX 3090 24 GB 1500$-3000$  
Before buying this or that equipment, I recommend testing your specific tasks in different GPU configurations on immers.cloud. They have H100, RTX 4090, RTX 3090, RTX 3080, Tesla A100, RTX A5000, Tesla A10, Tesla A2, RTX 2080 Ti, Tesla T4, Tesla V100.  
Extenders - When there are 4 PCIE slots, PCIEх16 gen4 gen3 risers will help to install 4 cards. They come in 20, 30, 40 cm lengths. There is also 60 cm - Lian Li 600 mm PCI-e 4.0 (PW-PCI-4-60X).  
llama.cpp will allow you to place some of the weights in the GPU and some in RAM, this makes sense if the RAM is slightly lacking, and the quantization is already on the verge of reducing quality, I ran codestral 22b with 5bit quantization on 16gb, specifying 48 of 57 layers on the gpu with the following speeds:  
RTX 4070 16G is not a very profitable option economically. RTX 4060 Ti 16G on local models is almost the same in inference speed, especially if the model does not fit into the memory entirely and only partial GPU Offload is used (and this is exactly what happens on 70+ models), with a price difference of more than one and a half times.
