def normalize_data(n_cases, n_people, scale):
    # TODO: Calculate the number of cases per its population
    norm_cases = []
    for idx, n in enumerate(n_cases):
        norm_cases.append(0)
    return norm_cases

regions  = ['Seoul', 'Gyeongi', 'Busan', 'Gyeongnam', 'Incheon', 'Gyeongbuk', 'Daegu', 'Chungnam', 'Jeonnam', 'Jeonbuk', 'Chungbuk', 'Gangwon', 'Daejeon', 'Gwangju', 'Ulsan', 'Jeju', 'Sejong']
n_people = [9550227,  13530519, 3359527,     3322373,   2938429,     2630254, 2393626,    2118183,   1838353,   1792476,    1597179,   1536270,   1454679,   1441970, 1124459, 675883,   365309] # 2021-08
n_covid  = [    644,       529,      38,          29,       148,          28,      41,         62,        23,        27,         27,        33,        16,        40,      20,      5,        4] # 2021-09-21

sum_people = sum(n_people) # TODO: The total number of people
sum_covid  = sum(n_covid) # TODO: The total number of new cases
norm_covid = normalize_data(n_covid, n_people, 1000000) # The new cases per 1 million people

# Print population by region
print('### Korean Population by Region')
print('* Total population:', sum_people)
print('| Region | Population | Ratio (%) |')
print('| ------ | ---------- | --------- |')
for idx1, pop1 in enumerate(n_people):
    ratio = pop1/sum_people*100 # TODO: The ratio of new cases to the total
    print('| %s | %d | %.1f |' % (regions[idx1], pop1, ratio))
print('')  

# TODO: Print COVID-19 new cases by region

print('### COVID-19 new cases by Region')
print('* Total new cases:', sum_covid)
print('| Region | Population | Ratio (%) | New Cases/ 1M |')
print('| ------ | ---------- | --------- |')
for idx2, pop2 in enumerate(n_covid):
    covid_ratio = pop2/sum_covid*100 # TODO: The ratio of new cases to the total   
    
    newcase= pop2/pop1*1000000
    print('| %s | %d | %.1f | %.1f |' % (regions[idx2], pop2, covid_ratio, newcase))
print('')