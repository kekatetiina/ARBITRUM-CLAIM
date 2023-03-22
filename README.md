# ARBITRUM-CLAIM
=========================НАСТРОЙКИ В ФАЙЛЕ config.py==========================

RPC_URL = 'RPC_URL'
Можно оставить пустым (RPC_URL = ''), тогда в data.txt данные нужно указывать в таком формате - p_key;address_to_send;rpc_url

WORK_MODE = 0  (1 | 0) 
0 - режим работы при котором после клейма отслыает на нужны адреса. Для каждого аккаунта свой адрес (если нужно, везде ставьте один). Пример в data.txt - p_key;address_to_send 
1 - режим работы при котором после клейма делает свап на 1inch 
P.S. ЕСЛИ УКАЗАН WORK_MODE = 1, СНАЧАЛА НУЖНО ЗАПУСТИТЬ inch_approve.py, ЧТОБЫ ЗАРАНЕЕ СДЕЛАТЬ АПРУВ НА SWAP "ARB"

GAS_PRICE_MULTIPLIER = 2 
Множитель цены газа. Целое число

INCH_SWAP_TO = 'ETH' 
Если WORK_MODE = 1, можно указать, на что будет свапать, ЛИБО ETH, ЛИБО USDC ('ETH' | 'USDC')

SLIPAGE = 3
Slipage (% проскальзывания) НА 1INCH

MIN_PRICE = 1
Минимальная цена в $ для свапа на 1INCH (пример 1.2 - ОБЯЗАТЕЛЬНО ЧЕРЕЗ ТОЧКУ!)

SEND_IF_BAD_PRICE = 1 
Ксли цена на 1inch будет меньше MIN_PRICE, то вместо свапа перекинет на кошелёк address_to_send | 0 - НЕТ, 1 - ДА Рекомендую ставить 1, если будете свапать на 1inch

==========================================================================

В data.txt вносим данные в таком формате: p_key;address_to_send;rpc_url, где: 
p_key - приватный ключ (не фраза) аккаунта, который сможет клеймить ARB 
address_to_send - адрес, на который после клейма будут отправлены токены (или после неудачного свапа) 
rpc_url - адрес RPC

