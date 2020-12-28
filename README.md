# jump917
import pygame  
pygame.init()
from pygame.locals import *
pygame.display.set_caption('The Cave')
width, height = 600, 600
screen=pygame.display.set_mode((width, height))
keys = [False, False, False, False]
playerpos=[50, 430]
background = pygame.image.load("background.png")
player = pygame.image.load("pixil-frame-0-2.png")
while 1:
    screen.fill(0)
    # 6 - draw the screen elements
    screen.blit(background, (0, 0))
    screen.blit(player, playerpos)
    # 7 - update the screen
    pygame.display.flip()
    # 8 - loop thr  b ough the events
    for event in pygame.event.get():
         if event.type == KEYDOWN:
            if event.key == K_UP:
                keys[0] = True
            elif event.key == K_LEFT:
                keys[1] = True
            elif event.key == K_DOWN:
                keys[2] = True
            elif event.key == K_RIGHT:
                keys[3] = True
         if event.type == pygame.KEYUP:
            if event.key==pygame.K_UP:
                keys[0]=False
            elif event.key==pygame.K_LEFT:
                keys[1]=False
            elif event.key==pygame.K_DOWN:
                keys[2]=False
            elif event.key==pygame.K_RIGHT:
                keys[3]=False
         if event.type == QUIT: 
            # if it is quit the game
            pygame.quit()
            exit(0)
        
             
                
    if keys[0]:
        playerpos[1] -= 5
    elif keys[2]:
        playerpos[1] += 5
    if keys[1]:
        playerpos[0] -= 5
    elif keys[3]:
        playerpos[0] += 5
    
