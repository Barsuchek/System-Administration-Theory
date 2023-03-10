# RAID

## RAID 0,1,5,10 что это?
Хранилище сервера - важнейшая часть с точки зрения отказоустойчивости. При не надлежащей настройке дисков, данные могут быть утеряны.

Для уверенности в том, что данные не пропадут, используют технологию **RAID(избыточный массив независимости дисков)**.

В RAID одни и те же данные дисков копируются сразу на множество дисков. В случае, если один из дисков выйдет из строя, потери данных не будет - копия есть на другом носителе.

Распространенные типы RAID массивов:
1. RAID 0 не является отказоустойчивым.
	В нем цельные данные дробятся на блоки и частями записываются на два или более диска. Тем самым 2 физически отдельных диска, объединяются в один.
	
	Если один из двух физических дисков выйдет из строя - вы потеряете все данные.
	
	RAID 0 есть смысл использовать если вы храните не критичные к потере данные к которым нужен доступ на высокой скорости.
	
	RAID 0 имеет низкую отказоустойчивость, но высокую производительность.

2. RAID 1 так же называют зеркальным, так как данные синхронно записываются на 2 и более диска сразу.
	Если один из дисков выйдет из строя, данные не будут потеряны.
	
	Если вы собираете в массив RAID 1 два диска, то в результате будете иметь только половину от их общей памяти.

3. В RAID 5 Вам понадобится три и более дисков. Данный RAID работает быстро и может хранить много данных.
	В RAID 5 данные не копируются между всеми дисками, а как в RAID 0 - последовательно записываются частями на каждый из дисков, но с одним дополнением - к данным равномерно записываются контрольная сумма(PARITY), которая нужна для восстановления данных в случае, если один из дисков выйдет из строя.
	
	Важный недостаток RAID 5 в том, что контрольная сумма занимает много места.
	
	**Например:** Если у вас 4 диска суммарным объемом в 4 терабайта, то использовать под хранение данных вы сможете только 3 терабайта, остально займет контрольная сумма.

4) RAID 10, данный RAID сочетает в себе функциональность RAID 1 и RAID 0.
	Для RAID 10 требуются минимум 4 диска, но их количество всегда должно быть четным.
	
	4 диска делятся на группы по 2 диска и каждая из групп объединяется в отказоустойчивый RAID 1. 
	
	Тем самым мы имеем 2 зеркальных RAID 1 массива, которые в свою очередь объединяются в RAID 0 массив.
	
	Тем самым RAID 10 имеет все скоростные преимущества RAID 0 и преимущества надежности RAID 1.
	
	Вы сможете использовать только 50% объема всех дисков(это особенность RAID 1).
