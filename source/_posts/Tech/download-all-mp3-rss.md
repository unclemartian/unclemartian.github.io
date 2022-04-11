---
title: 【Tech】 Download all MP3 files in RSS feed
date: 2022-03-01 00:00:00
tags: technology
---

# Why

For some reason, certain podcast are not accessible in China. Thus for good audio RSS content that I am afraid of missing out, downloading them and keep it offline is a nice idea. 

However, most RSS clients are not tailored for my use case, so instead of using any tools, I did some research and finally was able to download all MP3 from this podcast: 

1. https://raw.githubusercontent.com/Reyshawn/FanpieFilmFeed/master/fanPieFilm.rss
1. https://rss.shawnxli.com/fanpie-film-ma
1. https://anchor.fm/fanpaifilm

# First try

I did some research on [__podcatcher softwares__](https://en.wikipedia.org/wiki/List_of_podcast_clients), and no luck finding a good one. 

Failed. 

# Second try

Got some help from: 

https://www.commandlinefu.com/commands/view/14685/download-files-linked-in-a-rss-feed

And I used this command to exact all MP3 links:

    export HTTP_PROXY=http://127.0.0.1:58591; export HTTPS_PROXY=http://127.0.0.1:58591; export ALL_PROXY=socks5://127.0.0.1:51837

    curl -s https://raw.githubusercontent.com/Reyshawn/FanpieFilmFeed/master/fanPieFilm.rss | grep -o '<enclosure url="[^"]*' | grep -o '[^"]*$'

Here are the results: 

```
http://image.kaolafm.net/mz/audios/202112/eff8049d-3343-4821-bbce-428acb1f8d3a.mp3
http://image.kaolafm.net/mz/audios/202111/3b2f9eda-93cb-4e81-b70c-810efaefa523.mp3
http://image.kaolafm.net/mz/audios/202110/9b4bd4ae-141b-4b50-86c2-935b11e76e72.mp3
http://image.kaolafm.net/mz/audios/202108/655915fc-e473-4b4c-94e5-0d7fdcc74f2e.mp3
http://image.kaolafm.net/mz/audios/202107/c8035281-77ec-48b4-bf92-b3586f8572c3.mp3
http://image.kaolafm.net/mz/audios/202106/caadb011-bcec-4f95-835a-d97ab19e985d.mp3
http://image.kaolafm.net/mz/audios/202104/ba2ed655-47e8-42e6-a2ed-1e5fbfca1e44.mp3
http://image.kaolafm.net/mz/audios/202104/a3821a17-5afe-4410-954b-6889b51ebf41.mp3
http://image.kaolafm.net/mz/audios/202104/d834df6a-a77e-4be8-9058-b5d0bd2a3459.mp3
http://image.kaolafm.net/mz/audios/202104/375c1396-3dd1-4fe3-83b5-14be75a93fd5.mp3
http://image.kaolafm.net/mz/audios/202102/20622d34-e28f-4dfb-8932-3c43afab4ea1.mp3
http://image.kaolafm.net/mz/audios/202102/a93ca77b-d124-47c9-be91-a74373db467a.mp3
http://image.kaolafm.net/mz/audios/202101/bf6082d3-ce2d-493c-ba66-f0822bc8b86b.mp3
http://image.kaolafm.net/mz/audios/202101/e2870e97-ab25-45ea-aee7-b763c124cd2f.mp3
http://image.kaolafm.net/mz/audios/202012/8b5e6d36-6924-445b-ba70-ade3175549db.mp3
http://image.kaolafm.net/mz/audios/202012/e56f9b33-8cf6-45cb-bbed-e658e8f5e45d.mp3
http://image.kaolafm.net/mz/audios/202012/ed6b448e-cf41-46ce-b2d0-97b2fa368814.mp3
http://image.kaolafm.net/mz/audios/202011/f999682a-35ee-4116-92f6-87596a9d0c4e.mp3
http://image.kaolafm.net/mz/audios/202010/4588996d-82d4-4dfb-800a-5c05d3e1966f.mp3
http://image.kaolafm.net/mz/audios/202010/303a1beb-a1be-4ba5-a40c-71fc10c300fa.mp3
http://image.kaolafm.net/mz/audios/202009/abeb87bf-056e-4826-ac72-607624a15cb3.mp3
http://image.kaolafm.net/mz/audios/202009/c8808eee-0ca0-4520-bc46-86476a427658.mp3
http://image.kaolafm.net/mz/audios/202009/fa525980-016d-494b-9674-dd48843db3ed.mp3
http://image.kaolafm.net/mz/audios/202008/b1b715a2-4613-42af-82b4-73f6eb76878b.mp3
http://image.kaolafm.net/mz/audios/202008/c1d98d59-af07-4e16-8b88-a37872d5b929.mp3
http://image.kaolafm.net/mz/audios/202006/2a6a2592-0861-4a6f-a320-6857d37411f4.mp3
http://image.kaolafm.net/mz/audios/202004/8503d10b-c693-48a3-9bd6-7b9b0e69e581.mp3
http://image.kaolafm.net/mz/audios/202004/edd03e7e-48ab-41e3-8ac0-e64e0c025ccb.mp3
http://image.kaolafm.net/mz/audios/202004/49154781-92f2-4e6e-8440-2b661be18892.mp3
http://image.kaolafm.net/mz/audios/202003/c01d6e11-aed4-4b80-a360-2c8b6e2e3c8e.mp3
http://image.kaolafm.net/mz/audios/202003/4c40d6ad-3aab-43d2-9ac4-712a455be9f0.mp3
http://image.kaolafm.net/mz/audios/202002/941b860c-440a-4e81-b2ae-7fdbfb914b79.mp3
http://image.kaolafm.net/mz/audios/202002/3ef9353a-bbef-4e8f-b1eb-b9d93160d083.mp3
http://image.kaolafm.net/mz/audios/202002/4e981bc1-3d2e-4816-9dfc-916ea992b1d4.mp3
http://image.kaolafm.net/mz/audios/202001/61271245-08e1-4755-b940-5e3f34d98a67.mp3
http://image.kaolafm.net/mz/audios/202001/e498f238-4bed-4a15-b767-12ff44817ddc.mp3
http://image.kaolafm.net/mz/audios/201912/71bbd341-0fdb-461c-8bf4-0b3bf8c8d743.mp3
http://image.kaolafm.net/mz/audios/201912/cffb777f-6289-4196-96c0-312764deb5a5.mp3
http://image.kaolafm.net/mz/audios/201912/54c2812b-36b0-4942-bb6f-da86846d446c.mp3
http://image.kaolafm.net/mz/audios/201912/d9b93079-cfcb-4ce1-b89a-a7787e564731.mp3
http://image.kaolafm.net/mz/audios/201912/9e9bfb69-e1e3-489c-929a-0353e9897dc8.mp3
http://image.kaolafm.net/mz/audios/201912/24a4d89a-1e8f-4a21-bdac-37c3def79724.mp3
http://image.kaolafm.net/mz/audios/201912/09eb99d9-548f-4bd0-9214-ee0cfc2b6e30.mp3
http://image.kaolafm.net/mz/audios/201912/7bebed3a-d682-4011-94f5-fb759025d4dc.mp3
http://image.kaolafm.net/mz/audios/201911/c6696436-7e64-4ec5-bd50-cc32ec8bbc2b.mp3
http://image.kaolafm.net/mz/audios/201911/d38958a2-b57d-4db6-9ad4-3ce1d59f4540.mp3
http://image.kaolafm.net/mz/audios/201911/32442397-95ed-4504-a509-234f4c6a8f56.mp3
http://image.kaolafm.net/mz/audios/201911/f8a20712-05b8-4088-bb8d-915299463aa7.mp3
http://image.kaolafm.net/mz/audios/201910/891eafdd-bc18-478d-b493-3cd26bb9e249.mp3
http://image.kaolafm.net/mz/audios/201910/a1d482a1-2284-4e57-a8b8-f976e3599381.mp3
http://image.kaolafm.net/mz/audios/201910/38372d93-f08b-4db8-9fa6-28dde24a273f.mp3
http://image.kaolafm.net/mz/audios/201910/b79bfcfb-b12b-4aa9-880d-f4d588537341.mp3
http://image.kaolafm.net/mz/audios/201910/6bb10f4b-0cb3-4613-be71-addca89ee2c9.mp3
http://image.kaolafm.net/mz/audios/201910/ccf1b4dd-a8ce-4286-b370-c777cfc2d18f.mp3
http://image.kaolafm.net/mz/audios/201909/7d79039e-462f-496f-91d5-4a71efbd735d.mp3
http://image.kaolafm.net/mz/audios/201909/d5ea5d01-0b01-4a31-bbf7-dc8a0acda357.mp3
http://image.kaolafm.net/mz/audios/201909/2e06c72c-eba5-401b-9ad0-40f1192ef52d.mp3
http://image.kaolafm.net/mz/audios/201908/44ce9768-859d-47ee-83f7-7c919d11b964.mp3
http://image.kaolafm.net/mz/audios/201908/fd1ceafa-4c67-4bcd-8973-0a943707e0ef.mp3
http://image.kaolafm.net/mz/audios/201908/85504186-ebea-46ba-935a-66c6125fb73d.mp3
http://image.kaolafm.net/mz/audios/201908/67a68f1a-0747-4e09-ba1a-bcc10e6db422.mp3
http://image.kaolafm.net/mz/audios/201907/4f42768b-1a49-48e2-a704-52c714434a7f.mp3
http://image.kaolafm.net/mz/audios/201907/600d3f87-c869-401b-b387-c82a500e8ab1.mp3
http://image.kaolafm.net/mz/audios/201907/78b69791-c6d0-4e02-916e-d96bdad4350b.mp3
http://image.kaolafm.net/mz/audios/201907/9d4d3cbe-fb2c-46ba-9c4b-f21edf6daa2d.mp3
http://image.kaolafm.net/mz/audios/201906/3342f2fb-9e5b-42de-be3e-49c437d44ffc.mp3
http://image.kaolafm.net/mz/audios/201905/643d55c4-f165-4546-b8fa-774e1c11ccda.mp3
http://image.kaolafm.net/mz/audios/201905/a0f1f179-9e43-463c-9f26-0a7600e5db3a.mp3
http://image.kaolafm.net/mz/audios/201905/bc49458c-03a4-4956-9ae1-d881802ae13b.mp3
http://image.kaolafm.net/mz/audios/201905/248bf7af-c9a9-499b-ac7d-e03a4f406127.mp3
http://image.kaolafm.net/mz/audios/201904/908e9fe4-675d-4d70-953f-65db5895ab56.mp3
http://image.kaolafm.net/mz/audios/201904/06e0ce17-7de6-4048-ad3e-28769b82bfbb.mp3
http://image.kaolafm.net/mz/audios/201904/49e433c6-4212-4534-8f5a-b5ce5b5eb889.mp3
http://image.kaolafm.net/mz/audios/201904/b6604e90-7a17-4741-b407-2e43d57bb419.mp3
http://image.kaolafm.net/mz/audios/201904/17833de9-51ce-4468-be50-bcd7ef0923cc.mp3
http://image.kaolafm.net/mz/audios/201903/003c2dae-ed95-4a3f-aaf7-1dd1a360511f.mp3
http://image.kaolafm.net/mz/audios/201903/932421f3-a51b-4bb4-84a8-6394cd4859e5.mp3
http://image.kaolafm.net/mz/audios/201903/e103323a-3053-492d-9775-76701dcfa8d0.mp3
http://image.kaolafm.net/mz/audios/201903/82dab2c6-e81e-4d85-bc81-3c198354231b.mp3
http://image.kaolafm.net/mz/audios/201903/16abd3a7-0658-4f7e-92f2-9b16d998a119.mp3
http://image.kaolafm.net/mz/audios/201902/be8034db-a5df-4575-a5fd-68e3d7ccb2e4.mp3
http://image.kaolafm.net/mz/audios/201902/4272352a-9d13-4fd0-9cc3-9e215c05a1dc.mp3
http://image.kaolafm.net/mz/audios/201902/d935ed7e-6760-4cdc-9a22-d9675e3fddee.mp3
http://image.kaolafm.net/mz/audios/201902/af47c25a-873d-4dc3-b737-f55d7aae1d93.mp3
http://image.kaolafm.net/mz/audios/201902/0e79a2d5-7a76-4fa2-b8b5-ba83bd8f23e7.mp3
http://image.kaolafm.net/mz/audios/201901/dbab4815-f1a9-450c-ad05-0fca8a49855f.mp3
http://image.kaolafm.net/mz/audios/201901/b8512b37-0e3c-4e7f-870e-412cb0c1b23e.mp3
http://image.kaolafm.net/mz/audios/201901/fcf8bab3-44f7-4bce-b8c3-52c05a119913.mp3
http://image.kaolafm.net/mz/audios/201901/6cc247c6-fe4c-4016-b67f-200005b2d806.mp3
http://image.kaolafm.net/mz/audios/201901/40754b18-f6d6-417f-9517-1daceb14d41e.mp3
http://image.kaolafm.net/mz/audios/201901/4601783a-c2cc-411a-9248-dfdf354b27d0.mp3
http://image.kaolafm.net/mz/audios/201812/7e3beac8-9623-4048-b163-f7637f316abf.mp3
http://image.kaolafm.net/mz/audios/201812/66491aaf-0d71-424e-97d4-66955d1d503b.mp3
http://image.kaolafm.net/mz/audios/201812/b80d0058-de8d-4242-b1f9-9304404e4cfa.mp3
http://image.kaolafm.net/mz/audios/201812/dd643921-3a14-42a5-85ef-f22411c4fca6.mp3
http://image.kaolafm.net/mz/audios/201812/cf231d08-1452-475c-81f4-cfc444517934.mp3
http://image.kaolafm.net/mz/audios/201812/b822a240-a8ef-4b61-8ee9-29a1521c2ba2.mp3
http://image.kaolafm.net/mz/audios/201811/0e3e761a-5618-4f3f-a267-6548bbcb889e.mp3
http://image.kaolafm.net/mz/audios/201811/674833e7-cb23-4b79-b6d0-5c8c97c09faa.mp3
http://image.kaolafm.net/mz/audios/201811/53b7aa67-38f4-4151-a91d-120275d3e808.mp3
http://image.kaolafm.net/mz/audios/201811/704fbbc5-6602-4a27-8992-e16556a4b3cf.mp3
http://image.kaolafm.net/mz/audios/201811/02f52f37-cc4f-4cb9-974c-bd52f42ec2b8.mp3
http://image.kaolafm.net/mz/audios/201810/6d8dbe9e-bfb6-4c1e-a1ca-679098e482e1.mp3
http://image.kaolafm.net/mz/audios/201810/ddd462c1-3c35-4aff-a28a-6252c2d76127.mp3
http://image.kaolafm.net/mz/audios/201810/c289f907-59dd-4bd2-8f05-dc478929bc36.mp3
http://image.kaolafm.net/mz/audios/201810/ac744926-251e-44e0-8d11-09d1d2f41275.mp3
http://image.kaolafm.net/mz/audios/201810/2573cf56-19f9-4660-b8f6-7b62b91f03a4.mp3
http://image.kaolafm.net/mz/audios/201810/c3ee485a-4933-4143-b38a-ac2a12615c79.mp3
http://image.kaolafm.net/mz/audios/201810/0927bc53-bbb3-48ba-977d-a1e28cda4160.mp3
http://image.kaolafm.net/mz/audios/201810/9803c050-3bf5-4b4a-b294-fd8bcfbd5134.mp3
http://image.kaolafm.net/mz/audios/201809/5132753b-8334-4973-8be9-67996e685b71.mp3
http://image.kaolafm.net/mz/audios/201809/e7800a9e-f3c9-46dd-b6f8-1f411eff3a54.mp3
http://image.kaolafm.net/mz/audios/201809/4f6c940b-f87b-4604-82c5-9f2e2857c153.mp3
http://image.kaolafm.net/mz/audios/201809/946bdfcc-16af-4fcb-8be3-39df1538693e.mp3
http://image.kaolafm.net/mz/audios/201809/77869da7-f7fd-4197-a93f-481a8dc9f829.mp3
http://image.kaolafm.net/mz/audios/201809/bccb762f-74a2-4665-ad0d-1626715dec6e.mp3
http://image.kaolafm.net/mz/audios/201808/1e3aa0fa-9cf2-42be-95e0-745e5c72367e.mp3
http://image.kaolafm.net/mz/audios/201808/47e1d7f9-e9d0-4dd5-934a-50e4a26634dd.mp3
http://image.kaolafm.net/mz/audios/201808/c2bd5714-a1cf-4b08-aa42-5b0716d1ba6d.mp3
http://image.kaolafm.net/mz/audios/201808/2dda7900-eb96-4ffb-aec6-bbbf52dd32cd.mp3
http://image.kaolafm.net/mz/audios/201807/680cf0d4-edb7-4a6f-b8b2-c412d1e19b91.mp3
http://image.kaolafm.net/mz/audios/201807/eaac43c7-4229-40e1-862a-09eee64c56b7.mp3
http://image.kaolafm.net/mz/audios/201807/8ed518ff-d895-4a8c-a66f-77342428249a.mp3
http://image.kaolafm.net/mz/audios/201807/991e51ba-a66e-47ba-86e2-ae7fabf59ca5.mp3
http://image.kaolafm.net/mz/audios/201807/147b01d7-13f4-4243-a087-f30e133023bb.mp3
http://image.kaolafm.net/mz/audios/201807/82013211-c782-4a84-ad20-9001d1bdcd2e.mp3
http://image.kaolafm.net/mz/audios/201806/fe6c3325-c2c4-4710-9bed-472c138e8015.mp3
http://image.kaolafm.net/mz/audios/201806/0d43342d-9e0e-44eb-9f2a-cf058f5389d6.mp3
http://image.kaolafm.net/mz/audios/201806/a91c444e-cc97-4d88-bf96-5beab506e95d.mp3
http://image.kaolafm.net/mz/audios/201805/104336da-bc76-4e71-93ff-fae29a574532.mp3
http://image.kaolafm.net/mz/audios/201805/aa2e9018-ecc8-4026-b5f1-e1043060e041.mp3
http://image.kaolafm.net/mz/audios/201805/8980e872-110d-495f-968d-4d59f7ff6d97.mp3
http://image.kaolafm.net/mz/audios/201805/2c85000b-82f8-43db-8beb-162cee8f9d09.mp3
http://image.kaolafm.net/mz/audios/201805/b80b7cb2-3fc3-4f5e-bd54-a26ed880f3bc.mp3
http://image.kaolafm.net/mz/audios/201804/5b4613d8-fb06-4d01-b9ea-d55df2d325ac.mp3
http://image.kaolafm.net/mz/audios/201804/7473676c-645b-4d61-81e4-233dac9a127c.mp3
http://image.kaolafm.net/mz/audios/201804/6ea089de-00f1-4e4b-9499-0b63efabcf2e.mp3
http://image.kaolafm.net/mz/audios/201804/aff2e883-26f0-47f5-ab24-04e5225973c1.mp3
http://image.kaolafm.net/mz/audios/201803/0284f6ee-0d73-4077-a14c-ee8021714de0.mp3
http://image.kaolafm.net/mz/audios/201803/94ac6b81-76fd-4b36-8766-7489f867d113.mp3
http://image.kaolafm.net/mz/audios/201803/ad153671-ad6e-4a7c-b04b-bcb4b83b051e.mp3
http://image.kaolafm.net/mz/audios/201803/802322d1-7b06-46f9-9a60-3be67a55dd1c.mp3
http://image.kaolafm.net/mz/audios/201802/ee58697f-1608-4216-b47d-d0162824f324.mp3
http://image.kaolafm.net/mz/audios/201802/2ef16c61-7364-4cbb-94cf-00f4e403d833.mp3
http://image.kaolafm.net/mz/audios/201802/5ec28188-e823-4b8a-9440-68a2c5ab2e68.mp3
http://image.kaolafm.net/mz/audios/201802/094940b0-7ce5-4a2e-ae97-ae41fdd7e5c9.mp3
http://image.kaolafm.net/mz/audios/201801/c4b29cf3-5de5-4d77-8fbd-242b3cbbb55f.mp3
http://image.kaolafm.net/mz/audios/201801/5b31ea0b-b65e-41d9-8fd6-292243239d1e.mp3
http://image.kaolafm.net/mz/audios/201801/d0bfb852-c80c-42f3-ac6e-edc0d5b7d7e2.mp3
http://image.kaolafm.net/mz/audios/201712/b310cacb-0964-4392-b327-b8dc564aaf37.mp3
http://image.kaolafm.net/mz/audios/201712/e84065f5-fa4f-47c2-b77d-2e9c68c4d413.mp3
http://image.kaolafm.net/mz/audios/201712/885011f8-0358-4d8c-bcc7-bd8744db6f32.mp3
http://image.kaolafm.net/mz/audios/201712/90960718-0085-4de8-b321-dbc540a91702.mp3
http://image.kaolafm.net/mz/audios/201712/b4bee244-9342-40cf-9717-acb1cfad028a.mp3
http://image.kaolafm.net/mz/audios/201711/2a1cb7cf-ffb3-4be3-84fd-ae56643400ed.mp3
http://image.kaolafm.net/mz/audios/201711/a5f68a31-58ce-436f-8845-d71c24aaa7ba.mp3
http://image.kaolafm.net/mz/audios/201711/b073cf50-ef8f-48e8-919d-1219e8969554.mp3
http://image.kaolafm.net/mz/audios/201711/0e5d5987-3cc6-44f8-b593-279ba49d4b45.mp3
http://image.kaolafm.net/mz/audios/201711/3eceec65-a299-4320-ab0f-b2f2444dd267.mp3
http://image.kaolafm.net/mz/audios/201710/eff358de-a6ad-436f-8dc9-4e7c7e7c9a62.mp3
http://image.kaolafm.net/mz/audios/201710/c74c250c-d491-4bfc-9172-920fce5f562d.mp3
http://image.kaolafm.net/mz/audios/201710/73f7586a-43c4-412a-92e5-a454194c6492.mp3
http://image.kaolafm.net/mz/audios/201710/9589e4e4-876a-4629-b39e-5c08a5fb51c6.mp3
http://image.kaolafm.net/mz/audios/201709/d6c53b4a-cdd6-4ec6-ae29-700a204db003.mp3
http://image.kaolafm.net/mz/audios/201709/c225e7f5-659c-478c-8cd7-835ef3807cb2.mp3
http://image.kaolafm.net/mz/audios/201709/1239af2b-f202-4615-b21c-21e8a0614f59.mp3
http://image.kaolafm.net/mz/audios/201709/d68a706c-7823-45f6-bc3c-b2bc486097b3.mp3
http://image.kaolafm.net/mz/audios/201708/d2631bed-ba02-4680-be14-915d15691c6e.mp3
http://image.kaolafm.net/mz/audios/201708/409dbec4-40f7-4dc5-ac29-e932507e96c2.mp3
http://image.kaolafm.net/mz/audios/201708/9d4ac8e8-e447-4a6e-a872-6281dc590642.mp3
http://image.kaolafm.net/mz/audios/201708/de31d3e5-884e-4db7-a812-9fa5e5cfd7db.mp3
http://image.kaolafm.net/mz/audios/201707/15286125-281d-46ec-8e25-765f87f99769.mp3
http://image.kaolafm.net/mz/audios/201707/dad37d71-c1c9-40e2-bee8-8e3e5cb1360a.mp3
http://image.kaolafm.net/mz/audios/201707/4a2aa76d-5a5d-4ad3-8d1e-4404f4f81abd.mp3
http://image.kaolafm.net/mz/audios/201707/1f4c8b63-e7cb-459a-8785-97a44c764c36.mp3
http://image.kaolafm.net/mz/audios/201707/60e7ae9c-8bfb-4d29-abfd-705d73ffbd6f.mp3
http://image.kaolafm.net/mz/audios/201707/203a0cdf-2b15-4ba6-9ae1-bedf6fbc2463.mp3
http://image.kaolafm.net/mz/audios/201706/654a433b-2390-4d46-90a6-35a811228f93.mp3
http://image.kaolafm.net/mz/audios/201706/4f4f39fe-b821-4c51-8525-1541f836cc59.mp3
http://image.kaolafm.net/mz/audios/201706/402557bf-1949-4d3a-86c5-7bc40da394d8.mp3
http://image.kaolafm.net/mz/audios/201706/339e1c81-c68e-46a6-a2bc-bbdc05565b89.mp3
http://image.kaolafm.net/mz/audios/201705/ab23b320-317c-4a55-9e9d-aa51eaedb912.mp3
http://image.kaolafm.net/mz/audios/201705/32737bb3-067b-40be-a91c-94f38f220d72.mp3
http://image.kaolafm.net/mz/audios/201705/7d8b72db-85d7-4635-9fe5-adf213237b28.mp3
http://image.kaolafm.net/mz/audios/201705/831946f7-c2c0-4fbf-9989-8c04281fac3c.mp3
http://image.kaolafm.net/mz/audios/201704/602b5211-40a8-4d05-9b76-c398ba9308da.mp3
http://image.kaolafm.net/mz/audios/201704/33b55c24-b479-4221-b043-ed8a3010ee39.mp3
http://image.kaolafm.net/mz/audios/201704/d90b6d1e-ae14-421d-9877-076a5deaf1af.mp3
http://image.kaolafm.net/mz/audios/201704/70f68f37-6bbc-4d4b-8d9a-c293ce6e1e53.mp3
http://image.kaolafm.net/mz/audios/201704/54177eb8-d823-46fc-98c9-c60d5d42e4f0.mp3
http://image.kaolafm.net/mz/audios/201703/ad6cf0cd-cd8b-42fd-b799-8148e10076c4.mp3
http://image.kaolafm.net/mz/audios/201703/0b785c65-436a-42d6-94e7-cd3749df1b53.mp3
http://image.kaolafm.net/mz/audios/201703/a02d423d-54e0-4796-8138-346b1cba2b1a.mp3
http://image.kaolafm.net/mz/audios/201703/f0ebf602-9446-41e7-b103-9710342ff3e9.mp3
http://image.kaolafm.net/mz/audios/201703/4f1de1f5-cc2d-4be7-a6d4-587476ed1c21.mp3
http://image.kaolafm.net/mz/audios/201702/717c740c-3bf2-4480-8422-219b3dad3054.mp3
http://image.kaolafm.net/mz/audios/201702/05ae4fb6-39cc-41d3-993d-43c8daf4afe8.mp3
http://image.kaolafm.net/mz/audios/201702/af90f6ed-1736-4cad-bdc9-1a526e765d3d.mp3
http://image.kaolafm.net/mz/audios/201702/e1c76495-d524-4b09-927d-833e100f682f.mp3
http://image.kaolafm.net/mz/audios/201701/45e69016-6683-4514-990a-4f489d98d366.mp3
http://image.kaolafm.net/mz/audios/201701/419ded1f-007b-4b47-bc38-69a4ab01d977.mp3
http://image.kaolafm.net/mz/audios/201701/0de58dff-253f-482d-8911-c2f82cd4cddf.mp3
http://image.kaolafm.net/mz/audios/201701/f8a9bb1c-c155-49d1-8e7f-15a89c5c45b7.mp3
http://image.kaolafm.net/mz/audios/201612/a4d0077d-7933-4467-993c-c5eb1fafa6d6.mp3
http://image.kaolafm.net/mz/audios/201612/98dc8d54-b533-46b0-9a72-d3fd74345a6b.mp3
http://image.kaolafm.net/mz/audios/201612/727a9ad7-bdf2-4e23-b30c-c7fdc56f5ecf.mp3
http://image.kaolafm.net/mz/audios/201612/8db181dd-1648-4775-81ce-677be6ddd7de.mp3
http://image.kaolafm.net/mz/audios/201611/b184d2a5-ad67-4718-b382-35d8451a3941.mp3
http://image.kaolafm.net/mz/audios/201610/4c6a181e-f8ff-4b9e-9c20-4a05e8edac84.mp3
http://image.kaolafm.net/mz/audios/201610/d649b4b2-cfe3-4ece-8733-24a155475076.mp3
http://image.kaolafm.net/mz/audios/201610/4899a7df-11e7-4f36-b1bf-426b0402b868.mp3
http://image.kaolafm.net/mz/audios/201610/5aed13f5-ba79-474d-a72b-02510556f2d8.mp3
http://image.kaolafm.net/mz/audios/201610/110f8ef4-8478-495b-9790-809e4dc543b6.mp3
http://image.kaolafm.net/mz/audios/201609/f2687bea-5af4-4b2e-ac96-fda55236fb38.mp3
http://image.kaolafm.net/mz/audios/201609/d770259f-c0fb-4fac-a383-b19499fd0f35.mp3
http://image.kaolafm.net/mz/audios/201609/49e2b1fa-7ddb-47a6-9e1c-020f52b45ba0.mp3
http://image.kaolafm.net/mz/audios/201609/68642b2b-a7e0-448e-bd14-3ae2befe3a29.mp3
http://image.kaolafm.net/mz/audios/201608/e7a91cbb-10fa-49af-864e-469685517e40.mp3
http://image.kaolafm.net/mz/audios/201608/18301840-678f-48e8-8d58-f5bb1c2fcd28.mp3
http://image.kaolafm.net/mz/audios/201608/d5a0ecda-4f3b-469b-8a04-95321c2875d2.mp3
http://image.kaolafm.net/mz/audios/201608/7a1bec90-34c8-4992-88d4-44dd1c1aa2ff.mp3
http://image.kaolafm.net/mz/audios/201607/b06c1e57-f66f-4e9a-8346-1beebe5ba69a.mp3
http://image.kaolafm.net/mz/audios/201607/de3ea014-93b4-4745-909f-232e56cbfef8.mp3
http://image.kaolafm.net/mz/audios/201607/931fbddc-e9bf-40d2-b932-1b6e908a7194.mp3
http://image.kaolafm.net/mz/audios/201607/9e9901f5-0941-43ee-aa34-56da19de3822.mp3
http://image.kaolafm.net/mz/audios/201607/eaddaf3f-dff7-4013-bbca-50bd9429e359.mp3
http://image.kaolafm.net/mz/audios/201606/1c8c1083-8ef3-4565-8135-1f20215390f6.mp3
http://image.kaolafm.net/mz/audios/201606/1bfd9495-7e6d-4f34-937e-49150ab4556b.mp3
http://image.kaolafm.net/mz/audios/201606/c6e58270-bc1f-4867-87c8-d7e20fcc8bfd.mp3
http://image.kaolafm.net/mz/audios/201606/41e1b695-13d2-4793-a5dd-c55730912870.mp3
http://image.kaolafm.net/mz/audios/201605/3d4fd6fa-ad1b-433b-a1bd-20682ea2b6d3.mp3
http://image.kaolafm.net/mz/audios/201605/61ab1ea5-1871-44dd-b52c-a62ea861740a.mp3
http://image.kaolafm.net/mz/audios/201605/d8410566-eb52-4464-89b9-993521e26697.mp3
http://image.kaolafm.net/mz/audios/201604/72a83552-daaf-4ba0-a912-dec2b4fbbee4.mp3
http://image.kaolafm.net/mz/audios/201604/e30e0109-183a-4c82-bef5-39fd24197445.mp3
```

Simply dump those links into IDM softwares and the rest are set. 

## Problem

I got a bunch of files with naming like these: 

```
82013211-c782-4a84-ad20-9001d1bdcd2e.mp3
4c6a181e-f8ff-4b9e-9c20-4a05e8edac84.mp3
```

No timestamp, no title, no good. 

# Third try

I found this blog super useful:

https://rakhesh.com/coding/downloading-all-episodes-of-a-podcast/

Thus I wrote the following __rss_script.sh__:

```
for i in $(curl -s https://raw.githubusercontent.com/Reyshawn/FanpieFilmFeed/master/fanPieFilm.rss | grep -o '<enclosure url="[^"]*' | grep -o '[^"]*$'); do
    url=$i
    audiodir=$(echo $i | sed 's|http://image\.kaolafm\.net/mz/audios/||' | sed 's/\/.*\.mp3//')
    outfile=$(echo $i | sed 's|http://image\.kaolafm\.net/mz/audios/||')
    mkdir $audiodir
    wget -q $url -O $outfile
done
```

Simply:

    bash rss_script.sh

and you shall have a nice time. Enjoy.

## Result

All MP3s are in sub-folders like '201604' or '202112', however, I wasn't able to get the right title this time. 

# Reference

sed tutorial: https://www.digitalocean.com/community/tutorials/the-basics-of-using-the-sed-stream-editor-to-manipulate-text-in-linux

Original content: [here](/files/RSS反派影评Feed.txt)
