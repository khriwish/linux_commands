Part 1:

task 1:
run 'touch {morning,afternoon}-day-{1..30}'

task 2:
touch todos-$(date +"%m-%d-%y").txt

Part 2:

task 1:
run 'ls *9'

task 2:
run 'ls *1?'

task 3:
run 'ls afternoon*7'

task 4:
run 'mkdir Morning/'
run 'mv morning-day-* Morning/'

Part 3:

task 1:
run 'mkdir -p Year/{Winter,Spring,Summer,Fall}/{Yard,House}'

task 2:
run 'touch Year/{Winter,Spring,Summer,Fall}/{Yard,House}/{todos.txt,done.txt}'