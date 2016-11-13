--Executed every time the actor is available.       
下列技能CD好就使用

actions=auto_attack                               
动作。施放 自动攻击

actions+=/mind_freeze 							  
动作。施放 心灵冰冻 打断施法

actions+=/arcane_torrent,if=runic_power.deficit>20
动作。施放 奥术洪流 if 符文能量缺少值>20

actions+=/blood_fury                              
动作。施放 血腥狂怒 种族技能

actions+=/berserking							  
动作。施放 狂暴 巨魔种族天赋

actions+=/potion,name=old_war,if=buff.unholy_strength.react
动作。嗑药水 上古战神 if：player身上一旦有不洁之力 buff 马上施放
actions+=/outbreak,target_if=!dot.virulent_plague.ticking
动作。施放 爆发 if：target身上没有恶性瘟疫的debuff
 
actions+=/dark_transformation,if=equipped.137075&cooldown.dark_arbiter.remains>165
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND 黑暗仲裁者的cd时间>165s

actions+=/dark_transformation,if=equipped.137075&!talent.shadow_infusion.enabled&cooldown.dark_arbiter.remains>55
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND 天赋 暗影灌注没点出来 AND 黑暗仲裁者的cd时间>55s

actions+=/dark_transformation,if=equipped.137075&talent.shadow_infusion.enabled&cooldown.dark_arbiter.remains>35
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND 天赋 暗影灌注点出来了 AND 黑暗仲裁者的cd时间>35
 
actions+=/dark_transformation,if=equipped.137075&target.time_to_die<cooldown.dark_arbiter.remains-8
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND target预计死亡时间<黑暗仲裁者的cd时间-8s
 
actions+=/dark_transformation,if=equipped.137075&cooldown.summon_gargoyle.remains>160
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND 召唤石像鬼CD时间>160s
 
actions+=/dark_transformation,if=equipped.137075&!talent.shadow_infusion.enabled&cooldown.summon_gargoyle.remains>55
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND 天赋 暗影灌注没点出来 AND 召唤石像鬼CD时间>55s
 
actions+=/dark_transformation,if=equipped.137075&talent.shadow_infusion.enabled&cooldown.summon_gargoyle.remains>35
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND 天赋 暗影灌注点出来了 AND 召唤石像鬼CD时间>35s
 
actions+=/dark_transformation,if=equipped.137075&target.time_to_die<cooldown.summon_gargoyle.remains-8
动作。施放 黑暗突变：if 装备了 塔克瑟里特克斯的护肩 AND target预计死亡时间<召唤石像鬼CD时间-8s
 
actions+=/dark_transformation,if=!equipped.137075&rune<=3
动作。施放 黑暗突变：if 没有装备 塔克瑟里特克斯的护肩 AND 符文数目<=3
 
actions+=/blighted_rune_weapon,if=rune<=3
动作。施放 凋零符文武器：if 符文数目<=3 

actions+=/run_action_list,name=valkyr,if=talent.dark_arbiter.enabled&pet.valkyr_battlemaiden.active
动作。调用 valkyr 技能列表 ：if 天赋 黑暗仲裁者点出来了 AND 橙装的那个宠物存在

actions+=/call_action_list,name=generic
动作。调用 genric 技能列表
==========================================分割线======================================================
(--aoe技能列表)
actions.aoe=death_and_decay,if=spell_targets.death_and_decay>=2
动作。施放 枯萎凋零 ：if 枯萎凋零目标>=2 

actions.aoe+=/epidemic,if=spell_targets.epidemic>4
动作。施放 传染：if 传染的目标数目>4 

actions.aoe+=/scourge_strike,if=spell_targets.scourge_strike>=2&(dot.death_and_decay.ticking|dot.defile.ticking)
动作。施放 天灾打击：if 天灾打击的目标数目>=2 AND (target身上有恶性瘟疫的debuff OR target身上有亵渎的debuff)
actions.aoe+=/clawing_shadows,if=spell_targets.clawing_shadows>=2&(dot.death_and_decay.ticking|dot.defile.ticking)
动作。施放 暗影之爪：if 暗影之爪的目标数目>=2 AND (target身上有恶性瘟疫的debuff OR target身上有亵渎的debuff)

actions.aoe+=/epidemic,if=spell_targets.epidemic>2
动作。施放 传染：if 传染的目标数目>2
==========================================分割线========================================================
(--定义castigator技能列表)
actions.castigator=festering_strike,if=debuff.festering_wound.stack<=4&runic_power.deficit>23
动作。施放 脓疮打击：if target身上溃烂之伤的debuff层数<=4 AND 符文能量缺少值>23
 
actions.castigator+=/death_coil,if=!buff.necrosis.up&talent.necrosis.enabled&rune<=3
动作。施放 凋零缠绕：if player身上没有坏疽buff AND 天赋坏疽点了出来 AND 符文数目<=3
 
actions.castigator+=/scourge_strike,if=buff.necrosis.react&debuff.festering_wound.stack>=3&runic_power.deficit>23
动作。施放 天灾打击：if player身上一旦有坏疽的buff马上施放 AND target身上溃烂之伤的debuff层数>=3 AND 符文能量缺少值>23
 
actions.castigator+=/scourge_strike,if=buff.unholy_strength.react&debuff.festering_wound.stack>=3&runic_power.deficit>23
动作。施放 天灾打击：if player身上一旦有不洁之力马上施放 AND target身上溃烂之伤的debuff层数>=3 AND 符文能量缺少值>23
 
actions.castigator+=/scourge_strike,if=rune>=2&debuff.festering_wound.stack>=3&runic_power.deficit>23
动作。施放 天灾打击：if 符文数目>=2 AND target身上溃烂之伤的debuff层数>=3 AND 符文能量缺少值>23
 
actions.castigator+=/death_coil,if=talent.shadow_infusion.enabled&talent.dark_arbiter.enabled&!buff.dark_transformation.up&cooldown.dark_arbiter.remains>15
动作。施放 凋零缠绕：if 天赋 暗影灌注点出来了 AND 天赋 黑暗仲裁者点出来了 AND player身上没有暗影突变的buff AND 黑暗仲裁者的cd时间>15s
 
actions.castigator+=/death_coil,if=talent.shadow_infusion.enabled&!talent.dark_arbiter.enabled&!buff.dark_transformation.up
动作。施放 凋零缠绕：if 天赋 暗影灌注点出来了 AND 天赋 黑暗仲裁者没点出来 AND player身上没有暗影突变的buff
 
actions.castigator+=/death_coil,if=talent.dark_arbiter.enabled&cooldown.dark_arbiter.remains>15
动作。施放 凋零缠绕：if 天赋 黑暗仲裁者点出来了 AND 黑暗仲裁者的cd时间>15s
 
actions.castigator+=/death_coil,if=!talent.shadow_infusion.enabled&!talent.dark_arbiter.enabled
动作。施放 凋零缠绕：if 天赋 暗影灌注没点出来 AND 天赋 黑暗仲裁者没点出来
 ========================================分割线=====================================================
(--定义generic技能列表)
actions.generic=dark_arbiter,if=!equipped.137075&runic_power.deficit<30
动作。施放 黑暗仲裁者：if 没有装备 塔克瑟里特克斯的护肩 AND 符文能量缺少值<30
 
actions.generic+=/dark_arbiter,if=equipped.137075&runic_power.deficit<30&cooldown.dark_transformation.remains<2
动作。施放 黑暗仲裁者：if 装备了 塔克瑟里特克斯的护肩 AND 符文能量缺少值<30 AND 黑暗突变CD时间<2s

actions.generic+=/summon_gargoyle,if=!equipped.137075,if=rune<=3
动作。施放 召唤石像鬼：if 没有装备 塔克瑟里特克斯的护肩 AND 符文数目<=3
 
actions.generic+=/summon_gargoyle,if=equipped.137075&cooldown.dark_transformation.remains<10&rune<=3
动作。施放 召唤石像鬼：if 装备了 塔克瑟里特克斯的护肩 AND 黑暗突变CD时间<10 AND 符文数目<=3 
 
actions.generic+=/soul_reaper,if=debuff.festering_wound.stack>=7&cooldown.apocalypse.remains<2
动作。施放 灵魂收割：if target身上溃烂之伤的debuff层数>=7 AND 天启CD时间<2s
 
actions.generic+=/apocalypse,if=debuff.festering_wound.stack>=7
动作。施放 天启：if target身上溃烂之伤的debuff层数>=7
 
actions.generic+=/death_coil,if=runic_power.deficit<30
动作。施放 凋零缠绕：if 符文能量缺少值<30

actions.generic+=/death_coil,if=!talent.dark_arbiter.enabled&buff.sudden_doom.up&!buff.necrosis.up&rune<=3
动作。施放 凋零缠绕：if 天赋 黑暗仲裁者没点出来 AND player身上有末日突降的buff AND player身上没有坏疽buff AND 符文数目<=3 
 
actions.generic+=/death_coil,if=talent.dark_arbiter.enabled&buff.sudden_doom.up&cooldown.dark_arbiter.remains>5&rune<=3
动作。施放 凋零缠绕：if 天赋 黑暗仲裁者点出来了 AND player身上有末日突降的buff AND 黑暗仲裁者的cd时间>5s AND 符文数目<=3 
 
actions.generic+=/festering_strike,if=debuff.festering_wound.stack<7&cooldown.apocalypse.remains<5
动作。施放 脓疮打击：if target身上溃烂之伤的debuff层数<7 AND 天启CD时间<5s
 
actions.generic+=/wait,sec=cooldown.apocalypse.remains,if=cooldown.apocalypse.remains<=1&cooldown.apocalypse.remains
动作。等待 时间是 天启CD时间：if 天启CD时间<=1s AND 天启正在cd
 
actions.generic+=/soul_reaper,if=debuff.festering_wound.stack>=3
动作。施放 灵魂收割：if target身上溃烂之伤的debuff层数>=3 
 
actions.generic+=/festering_strike,if=debuff.soul_reaper.up&!debuff.festering_wound.up
动作。施放 脓疮打击：if target 身上有灵魂收割debuff AND target身上没有溃烂之伤的debuff
 
actions.generic+=/scourge_strike,if=debuff.soul_reaper.up&debuff.festering_wound.stack>=1
动作。施放 天灾打击：if target身上有灵魂收割buff AND target身上溃烂之伤的debuff层数>=1 
 
actions.generic+=/clawing_shadows,if=debuff.soul_reaper.up&debuff.festering_wound.stack>=1
动作。施放 暗影之爪：if target身上有灵魂收割debuff AND target身上溃烂之伤的debuff层数>=1 
 
actions.generic+=/defile
动作。施放 亵渎
 
actions.generic+=/call_action_list,name=aoe,if=active_enemies>=2
动作。调用 aoe 技能列表 ：if 目标敌人数目>=2
 
actions.generic+=/call_action_list,name=instructors,if=equipped.132448
动作。调用 instructors 技能列表 ：if 装备了 教官的第四课
 
actions.generic+=/call_action_list,name=standard,if=!talent.castigator.enabled&!equipped.132448
动作。调用 standard 技能列表 ：if 天赋 惩戒连枷没有点出来 AND 没有装备 教官的第四课
 
actions.generic+=/call_action_list,name=castigator,if=talent.castigator.enabled&!equipped.132448
动作。调用 castigator：if 天赋 惩戒连枷点出来了 AND 没有装备 教官的第四课
 =========================================分割线===================================================
(--定义instructors技能列表) 
actions.instructors=festering_strike,if=debuff.festering_wound.stack<=4&runic_power.deficit>23
动作。施放 脓疮打击 ：if target身上溃烂之伤的debuff层数<=4 AND 符文能量缺少值>23
 
actions.instructors+=/death_coil,if=!buff.necrosis.up&talent.necrosis.enabled&rune<=3
动作。施放 凋零缠绕：if player身上没有坏疽buff AND 天赋坏疽点了出来 AND 符文数目<=3 
 
actions.instructors+=/scourge_strike,if=buff.necrosis.react&debuff.festering_wound.stack>=5&runic_power.deficit>29
动作。施放 天灾打击：if player身上一旦有坏疽的buff马上施放 AND target身上溃烂之伤的debuff层数>=5 AND 符文能量缺少值>29
 
actions.instructors+=/clawing_shadows,if=buff.necrosis.react&debuff.festering_wound.stack>=5&runic_power.deficit>29
动作。施放 暗影之爪：if player身上一旦有坏疽的buff马上施放 AND target身上溃烂之伤的debuff层数>=5 AND 符文能量缺少值>29
 
actions.instructors+=/scourge_strike,if=buff.unholy_strength.react&debuff.festering_wound.stack>=5&runic_power.deficit>29
动作。施放 天灾打击：if player身上一旦有不洁之力马上施放 AND target身上溃烂之伤的debuff层数>=5 AND 符文能量缺少值>29

actions.instructors+=/clawing_shadows,if=buff.unholy_strength.react&debuff.festering_wound.stack>=5&runic_power.deficit>29
动作。施放 暗影之爪：if player身上一旦有不洁之力马上施放 AND target身上溃烂之伤的debuff层数>=5 AND 符文能量缺少值>29

actions.instructors+=/scourge_strike,if=rune>=2&debuff.festering_wound.stack>=5&runic_power.deficit>29
动作。施放 天灾打击 ：if 符文数目>=2 AND target身上溃烂之伤的debuff层数>=5 AND 符文能量缺少值>29

actions.instructors+=/clawing_shadows,if=rune>=2&debuff.festering_wound.stack>=5&runic_power.deficit>29
动作。施放 暗影之爪：if 符文数目>=2 AND target身上溃烂之伤的debuff层数>=5 AND 符文能量缺少值>29
 
actions.instructors+=/death_coil,if=talent.shadow_infusion.enabled&talent.dark_arbiter.enabled&!buff.dark_transformation.up&cooldown.dark_arbiter.remains>15
动作。施放 凋零缠绕：if 天赋 暗影灌注点出来了 AND 天赋 黑暗仲裁者点出来了 AND player身上没有暗影突变的buff AND 黑暗仲裁者的cd时间>15s

actions.instructors+=/death_coil,if=talent.shadow_infusion.enabled&!talent.dark_arbiter.enabled&!buff.dark_transformation.up
动作。施放 凋零缠绕：if 天赋 暗影灌注点出来了 AND 天赋 黑暗仲裁者没点出来 AND player身上没有暗影突变的buff 

actions.instructors+=/death_coil,if=talent.dark_arbiter.enabled&cooldown.dark_arbiter.remains>15
动作。施放 凋零缠绕：if 天赋 黑暗仲裁者点出来了 AND 黑暗仲裁者的cd时间>15s

actions.instructors+=/death_coil,if=!talent.shadow_infusion.enabled&!talent.dark_arbiter.enabled
动作。施放 凋零缠绕：if 天赋 暗影灌注没点出来 AND 天赋 黑暗仲裁者没点出来
=========================================分割线================================================
(--定义standard技能列表)
actions.standard=festering_strike,if=debuff.festering_wound.stack<=4&runic_power.deficit>23
动作。施放 脓疮打击：if target身上溃烂之伤的debuff层数<=4 AND 符文能量缺少值>23

actions.standard+=/death_coil,if=!buff.necrosis.up&talent.necrosis.enabled&rune<=3
动作。施放 凋零缠绕：if player身上没有坏疽buff AND 天赋坏疽点了出来 AND 符文数目<=3

actions.standard+=/scourge_strike,if=buff.necrosis.react&debuff.festering_wound.stack>=1&runic_power.deficit>15
动作。施放 天灾打击：if player身上一旦有有坏疽buff马上施放 AND target身上溃烂之伤的debuff层数>=1 AND 符文能量缺少值>15

actions.standard+=/clawing_shadows,if=buff.necrosis.react&debuff.festering_wound.stack>=1&runic_power.deficit>15
动作。施放 暗影之爪：if player身上一旦有坏疽的buff马上施放 AND target身上溃烂之伤的debuff层数>=1 AND 符文能量缺少值>15

actions.standard+=/scourge_strike,if=buff.unholy_strength.react&debuff.festering_wound.stack>=1&runic_power.deficit>15
动作。施放 天灾打击：if player身上一旦有不洁之力马上施放 AND target身上溃烂之伤的debuff层数>=1 AND 符文能量缺少值>15

actions.standard+=/clawing_shadows,if=buff.unholy_strength.react&debuff.festering_wound.stack>=1&runic_power.deficit>15
动作。施放 暗影之爪：if player身上一旦有不洁之力马上施放 AND target身上溃烂之伤的debuff层数>=1 AND 符文能量缺少值>15

actions.standard+=/scourge_strike,if=rune>=2&debuff.festering_wound.stack>=1&runic_power.deficit>15
动作。施放 天灾打击：if 符文数目>=2 AND target身上溃烂之伤的debuff层数>=1 AND 符文能量缺少值>15

actions.standard+=/clawing_shadows,if=rune>=2&debuff.festering_wound.stack>=1&runic_power.deficit>15
动作。施放 暗影之爪：if 符文数目>=2 AND target身上溃烂之伤的debuff层数>=1 AND 符文能量缺少值>15

actions.standard+=/death_coil,if=talent.shadow_infusion.enabled&talent.dark_arbiter.enabled&!buff.dark_transformation.up&cooldown.dark_arbiter.remains>15
动作。施放 凋零缠绕：if 天赋 暗影灌注点出来了 AND 天赋 黑暗仲裁者点出来了 AND player身上没有暗影突变的buff AND 黑暗仲裁者的cd时间>15s

actions.standard+=/death_coil,if=talent.shadow_infusion.enabled&!talent.dark_arbiter.enabled&!buff.dark_transformation.up
动作。施放 凋零缠绕：if 天赋 暗影灌注点出来了 AND 天赋 黑暗仲裁者没点出来 AND player身上没有暗影突变的buff

actions.standard+=/death_coil,if=talent.dark_arbiter.enabled&cooldown.dark_arbiter.remains>15
动作。施放 凋零缠绕：if 天赋 黑暗仲裁者点出来了 AND 黑暗仲裁者的cd时间>15s

actions.standard+=/death_coil,if=!talent.shadow_infusion.enabled&!talent.dark_arbiter.enabled
动作。施放 凋零缠绕：if 天赋 暗影灌注没点出来 AND 天赋 黑暗仲裁者没点出来
=============================================分割线==================================
(--定义valkyr技能列表)
actions.valkyr=death_coil
动作。施放 凋零缠绕

actions.valkyr+=/apocalypse,if=debuff.festering_wound.stack=8
动作。施放 天启：if target身上溃烂之伤的debuff层数=8 

actions.valkyr+=/festering_strike,if=debuff.festering_wound.stack<8&cooldown.apocalypse.remains<5
动作。施放 脓疮打击：if target身上溃烂之伤的debuff层数<8 AND 天启CD时间<5s

actions.valkyr+=/call_action_list,name=aoe,if=active_enemies>=2
动作。调用 aoe技能列表： if 目标敌人数目>=2

actions.valkyr+=/festering_strike,if=debuff.festering_wound.stack<=3
动作。施放 脓疮打击：if target身上溃烂之伤的debuff层数<=3 

actions.valkyr+=/scourge_strike,if=debuff.festering_wound.up
动作。施放 天灾打击：if target身上有溃烂之伤的debuff

actions.valkyr+=/clawing_shadows,if=debuff.festering_wound.up
动作。施放 暗影之爪：if target身上有溃烂之伤的debuff