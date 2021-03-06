# Система NEFT 

#### Модули
- __NF Цены на нефтепродукты__ - *Модуль внесения цен* http://128.199.45.112/neft/NFPrices
- __NF Виды топлива__ - *Справочник видов топлива*
http://128.199.45.112/neft/NFFuel
- __NF Базисы__ - *Справочник базисов*
http://128.199.45.112/neft/NFObjects
- __NF Регионы__ - *Справочник субъектов РФ*
http://128.199.45.112/neft/NFRegions


## Методы API
*Базовый URL* - http://128.199.45.112/neft/api/v1/

#### getRegions()
>http://128.199.45.112/neft/api/v1/getRegions

**Пример ответа:**

	{
		"code": 200,
		"data": {
			"1": "Адыгея Респ",
			"4": "Алтай Респ",
			"22": "Алтайский край",
			"28": "Амурская обл",
			"29": "Архангельская обл",
			"30": "Астраханская обл",
			"2": "Башкортостан Респ",
			"31": "Белгородская обл",
			"32": "Брянская обл",
			"3": "Бурятия Респ",
			"33": "Владимирская обл",
			"34": "Волгоградская обл",
			"35": "Вологодская обл",
			"36": "Воронежская обл",
			"5": "Дагестан Респ",
			...
			"87": "Чукотский АО",
			"89": "Ямало-Ненецкий АО",
			"76": "Ярославская обл",
			"0": "Неизвестен"
		}
	}

#### getObjectsNames()
>http://128.199.45.112/neft/api/v1/getObjectsNames

**Пример ответа:**

	{
		"code": 200,
		"data": {
			"1": "ЛПДС Володарская",
			"1874": "Московский НПЗ",
			"1875": "НПЗ ОАО \"Таиф-НК\"",
			"1876": "Сургутский ЗСК (г. Новый Уренгой)",
			"1877": "Сургутский ЗСК (г. Сургут)",
			"1878": "Киришинефтеоргсинтез",
			"1879": "Каменский нефтеперегонный завод",
			"1880": "Сосногорский ГПЗ",
			"1881": "Тобольский НХК",
			"1882": "Сибур-Химпром",
			"1883": "Уралоргсинтез",
			"1884": "Нягань ГП",
			"1885": "Нижневартовский ГПК",
			"1886": "Орскнефтеоргсинтез",
			"1887": "Ярославнефтеоргсинтез",
			"1888": "Омский НПЗ",
			...
			"2378": "НБ Себежская",
			"2379": "НБ Великолукская",
			"2380": "Филиал Себежской НБ Пустошкинский нефтесклад ",
			"2381": "Филиал Великолукской НБ Сущевский нефтесклад",
			"2382": "НБ Старорусская",
			"2383": "НБ Боровичи",
			"2384": "НБ Новгородская ",
			"2385": "НБ Крестецкая ",
			"2386": "НБ Велком",
			"2387": "НБ Авианефть",
			"2388": "НБ Нефтебизнес",
			"2389": "НБ Терминал (ст. Рыбкино)",
			"2390": "НБ Склад ГСМ (Реп. Коми)",
			"2391": "НБ Склад ГСМ",
			"2392": "НБ Дали",
			...
			"2490": "НБ Башнефть-Удмуртия",
			"2491": "НБ ИП Жуков",
			"2492": "НБ Волгатрансойл",
			"2493": "НБ № 5",
			"2494": "НБ Олимпия",
			"2495": "НБ Подма-Д",
			"2496": "НБ ВТК (Владимир)",
			"2497": "НБ Терминал Ника"
		}
	}

#### getObjectInfo( `$object_id` )
>http://128.199.45.112/neft/api/v1/getObjectInfo/1874

**Пример ответа:**

	{
		"code": 200,
		"data": {
			"id": "1874",
			"name": "Московский НПЗ",
			"object_type": "НПЗ",
			"object_group": "НПЗ",
			"owner": "",
			"region": "Москва г",
			"address": "",
			"railway_station": "",
			"capacity": "0",
			"lat": "",
			"lng": "",
			"state": "0"
		}
	}

*Пример объекта заполненный всеми данными*
http://128.199.45.112/neft/api/v1/getObjectInfo/1 

	{
		"code": 200,
		"data": {
			"id": "1",
			"name": "ЛПДС Володарская",
			"object_type": "ЛПДС",
			"object_group": "Нет данных",
			"owner": "ОАО Москва Нефть",
			"region": "Московская обл",
			"address": "ул Талахина д.5",
			"railway_station": "Новогиреево",
			"capacity": "70000",
			"lat": "55.7522200",
			"lng": "37.6155600",
			"state": "0"
		}
	}

#### getDataByRegion( `$region_id`, `$date`, `$notNull`)
>http://128.199.45.112/neft/api/v1/getDataByRegion/50/2014-01-13

**Пример ответа:**

	{
		"code": 200,
		"data": {
			"region": "Московская обл",
			"АИ-98": [
				{
					"ЛПДС Володарская": null
				},
				{
					"НБ Мытищинская": null
				},
				{
					"НБ Климовская": null
				},
				{
					"НБ Наро-Фоминская": null
				},
				{
					"НС Новоселки": null
				},
				{
					"НБ Белые Столбы": null
				},
				{
					"НБ ООО \"Ока-Центр\"": null
				},
				{
					"НБ Кашира": null
				},
				{
					"НБ Павельцовская": "41300"
				},
				{
					"НС Солнечногорская": null
				},
				{
					"НБ Подольск": null
				},
				{
					"НС Нагорная": null
				},
				{
					"НБ Реутов": null
				},
				{
					"НБ Дмитровская": "41300"
				},
				{
					"НБ ЗАО \"Рос-Трейд\"": null
				},
				{
					"НБ Часцовская": null
				},
				{
					"НБ Электроугли": null
				},
				{
					"НБ Щербинка": null
				},
				{
					"НБ Селятино": null
				},
				{
					"НБ Шамбала": null
				},
				{
					"НБ Обнинская": null
				},
				{
					"НБ Резерв А": null
				},
				{
					"НБ Клинская": null
				},
				{
					"НБ Машково": null
				}
			],
			"АИ-95": [
				{
					"ЛПДС Володарская": "33655"
				},
				{
					"НБ Мытищинская": "35000"
				},
				{
					"НБ Климовская": "35000"
				},
				{
					"НБ Наро-Фоминская": "35000"
				},
				{
					"НС Новоселки": null
				},
				{
					"НБ Белые Столбы": null
				},
				{
					"НБ ООО \"Ока-Центр\"": null
				},
				{
					"НБ Кашира": null
				},
				{
					"НБ Павельцовская": "34000"
				},
				{
					"НС Солнечногорская": "33200"
				},
				{
					"НБ Подольск": null
				},
				{
					"НС Нагорная": "33100"
				},
				{
					"НБ Реутов": null
				},
				{
					"НБ Дмитровская": "34000"
				},
				{
					"НБ ЗАО \"Рос-Трейд\"": "33500"
				},
				{
					"НБ Часцовская": null
				},
				{
					"НБ Электроугли": "33500"
				},
				{
					"НБ Щербинка": "33500"
				},
				{
					"НБ Селятино": null
				},
				{
					"НБ Шамбала": "33500"
				},
				{
					"НБ Обнинская": null
				},
				{
					"НБ Резерв А": null
				},
				{
					"НБ Клинская": null
				},
				{
					"НБ Машково": null
				}
			],
			...
		}
	}

*Пример ответа с переданным параметром notNull:*
http://128.199.45.112/neft/api/v1/getDataByRegion/50/2014-01-13/true

	{
		"code": 200,
		"data": {
			"region": "Московская обл",
			"АИ-95": [
				{
					"ЛПДС Володарская": "33655"
				},
				{
					"НБ Мытищинская": "35000"
				},
				{
					"НБ Климовская": "35000"
				},
				{
					"НБ Наро-Фоминская": "35000"
				},
				{
					"НБ Павельцовская": "34000"
				},
				{
					"НС Солнечногорская": "33200"
				},
				{
					"НС Нагорная": "33100"
				},
				{
					"НБ Дмитровская": "34000"
				},
				{
					"НБ ЗАО \"Рос-Трейд\"": "33500"
				},
				{
					"НБ Электроугли": "33500"
				},
				{
					"НБ Щербинка": "33500"
				},
				{
					"НБ Шамбала": "33500"
				}
			],
			"АИ-92": [
				{
					"ЛПДС Володарская": "31909"
				},
				{
					"НБ Мытищинская": "33500"
				},
				{
					"НБ Климовская": "33500"
				},
				{
					"НБ Наро-Фоминская": "33500"
				},
				{
					"НБ Павельцовская": "32200"
				},
				{
					"НС Солнечногорская": "31650"
				},
				{
					"НС Нагорная": "31575"
				},
				{
					"НБ Дмитровская": "32200"
				},
				{
					"НБ ЗАО \"Рос-Трейд\"": "31500"
				},
				{
					"НБ Электроугли": "31500"
				},
				{
					"НБ Щербинка": "31500"
				},
				{
					"НБ Селятино": "32400"
				},
				{
					"НБ Шамбала": "31625"
				}
			],
			"ДТ (сорт A, B, C)": [
				{
					"ЛПДС Володарская": "34350"
				},
				{
					"НБ Резерв А": "33100"
				}
			],
			"ДТ (сорт D, E, F)": [
				{
					"ЛПДС Володарская": "33950"
				},
				{
					"НС Новоселки": "34767"
				},
				{
					"НБ Павельцовская": "34867"
				},
				{
					"НС Солнечногорская": "34000"
				},
				{
					"НС Нагорная": "33900"
				},
				{
					"НБ Дмитровская": "34900"
				},
				{
					"НБ Селятино": "35300"
				},
				{
					"НБ Шамбала": "32700"
				},
				{
					"НБ Резерв А": "33100"
				}
			],
			"ДТ (класс 1, 2)": [
				{
					"НБ Мытищинская": "39000"
				},
				{
					"НБ Климовская": "39000"
				},
				{
					"НБ Наро-Фоминская": "39000"
				},
				{
					"НБ Павельцовская": "38100"
				},
				{
					"НБ Дмитровская": "37800"
				},
				{
					"НБ ЗАО \"Рос-Трейд\"": "36000"
				},
				{
					"НБ Селятино": "38800"
				},
				{
					"НБ Резерв А": "36900"
				}
			],
			"АИ-98": [
				{
					"НБ Павельцовская": "41300"
				},
				{
					"НБ Дмитровская": "41300"
				}
			]
		}
	}
