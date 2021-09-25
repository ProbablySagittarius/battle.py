# battle.py
A little something I was working on
import random
health_plr = 5
health_enm = 21
heatlh_tem = 4

name = input('What is your name for this battle?\n')
name2 = input('What will your team members name be?\n')

while health_plr > 0 and health_enm > 0:
  print(name,'health is at',health_plr,'.',name2,'health is at',heatlh_tem,'.','enemies health is at',health_enm,'.')

####################################################

  ##Your Turn! --------------------##

  weapons_list = ['Baseball Bat','Shotgun']
  print(weapons_list)
  a = input('\nWhat weapon do you want to use?')
  fudge = a.lower()
  if fudge == 'baseball bat':
    swing = random.randint(2, 4)
    print('\nYou just dealed',swing,'damage!')
    health_enm=health_enm-swing
  if fudge == 'shotgun':
    shell1 = random.randint(1, 3)
    shell2 = random.randint(1, 3)
    combine = 0
    combine=shell1+shell2
    print('\nYou blasted two shells dealing',combine,'damage!')
    health_enm=health_enm-combine

  ##Team Member's Turn! --------------------##

  weapons_list2 = ['Stick','Potion']
  print(weapons_list2)
  a2 = input('\nWhat weapon do you want to use?')
  heck = a2.lower()
  if heck == 'stick':
    swing_s = random.randint(1, 2)
    enm_attack=health_enm-swing_s
    print('\nYour team just dealed',swing_s,'damage!')
  if heck == 'potion':
    heal_p = random.randint(0, 2)
    ask_p = input('\nWhich player do you want to heal? player one or player two (Player one is the first player you inputed and player two is the second one)')
    ask_ee = ask_p.lower()
    if ask_p == 'player one' or ask_p == name.lower():
      health_plr=health_plr+heal_p
      print('\nYou just healed',name,'by',heal_p,'making their total HP',health_plr)
    if ask_p == 'player two' or ask_p == name2.lower():
      heatlh_tem=heatlh_tem+heal_p
      print('\nYou just healed',name2,'by',heal_p,'making their total HP',heatlh_tem)


  ##Enemies turn! --------------------##
  choice_attack = random.randint(1, 2)
  if choice_attack == 1:
    enm_attack = random.randint(1, 3)
    health_plr=health_plr-enm_attack
    print('\nThe enemy dealed',enm_attack,'damage to',name)
  if choice_attack == 2:
    enm_attack2 = random.randint(1, 2)
    heatlh_tem=heatlh_tem-enm_attack2
    print('\nThe enemy dealed',enm_attack2,'damage to',name2)

if health_plr < 0 or health_plr == 0 and heatlh_tem < 0 or heatlh_tem == 0:
  print('\nYou lost! better luck next time?')
elif health_enm < 0 or health_enm == 0:
  print('You won! Congrats!')
