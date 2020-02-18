#!/usr/bin/env python3
# -*- coding: utf-8 -*-
# @Date  : 2018/10/23

import random
import os
import time

import pygame

# 清屏


def clear_screen():
    # 图省事哦
    if os.sep == '/':
        os.system('clear')
    else:
        os.system('cls')


# 模拟延时效果


def delay_waiting(content, frequency):
    print('%s.' % content, end='', flush=True)
    for x in range(1, frequency):
        time.sleep(1)
        print('.', end='', flush=True)
    time.sleep(1)
    print(' succeeded.')

# 模拟登陆锡安主机


def login_zion():
    clear_screen()
    delay_waiting('connecting to Zion host', 2)
    time.sleep(0.5)
    print('enter username: Neo')
    time.sleep(0.2)
    print('enter password: zyq200021')
    time.sleep(0.2)
    delay_waiting('logging in.', 2)
    time.sleep(0.7)
    clear_screen()
    print('Hello, Neo.')
    time.sleep(1)


# 模拟登陆锡安主机
login_zion()
# 清屏
clear_screen()


PANEL_width = 1000
PANEL_highly = 600
FONT_PX = 15

pygame.init()

# 创建一个可视窗口
winSur = pygame.display.set_mode((PANEL_width, PANEL_highly))

font = pygame.font.SysFont("123.ttf", 25)

bg_suface = pygame.Surface((PANEL_width, PANEL_highly), flags=pygame.SRCALPHA)

pygame.Surface.convert(bg_suface)

bg_suface.fill(pygame.Color(0, 0, 0, 28))

winSur.fill((0, 0, 0))

# 数字版
#texts = [font.render(str(i), True, (0, 255, 0)) for i in range(10)]

# 字母版
letter = ['q', 'w', '1', 'e', '4', 'r', '9', 't', '6', 'y', '2', 'u', '8', 'i', '3', 'o', '5', 'p', 'a', 's', 'd', 'f',
          'g', 'h', 'j', 'k', 'l', 'z', 'x', 'c',
          'v', 'b', 'n', '0', 'm', 'α', ' Γ', 'β ', 'Δ', 'δ', 'ε', 'ζ', 'η', 'Θ', 'ι', '∧', 'μ', 'ξ', 'π', 'ρ', '∑',
          'τ ', 'υ', 'Φ', ' Ψ', 'Ω']
texts = [
    font.render(str(letter[i]), True, (0, 255, 0)) for i in range(56)
]

# 按屏幕的宽带计算可以在画板上放几列坐标并生成一个列表
column = int(PANEL_width / FONT_PX)
drops = [0 for i in range(column)]

while True:
    # 从队列中获取事件
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()
        elif event.type == pygame.KEYDOWN:

            chang = pygame.key.get_pressed()
            if (chang[32]):
                exit()

    # 将暂停一段给定的毫秒数
    pygame.time.delay(30)

    # 重新编辑图像第二个参数是坐上角坐标
    winSur.blit(bg_suface, (0, 0))

    for i in range(len(drops)):
        text = random.choice(texts)

        # 重新编辑每个坐标点的图像
        winSur.blit(text, (i * FONT_PX, drops[i] * FONT_PX))

        drops[i] += 1
        if drops[i] * 10 > PANEL_highly or random.random() > 0.95:
            drops[i] = 0

    pygame.display.flip()
