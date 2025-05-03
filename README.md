import pygame

pygame.init()

HEIGHT = 600
WIDTH = 600

display_surface=pygame.display.set_mode((600,600))
pygame.display.set_caption("app matcher")

img1 = pygame.image.load('angry birds.jpg')
angry_birds = pygame.transform.scale(img1, (100,100))
display_surface.blit(angry_birds, (90,90))

img2 = pygame.image.load('candy crush.jpg')
candy_crush = pygame.transform.scale(img2, (100,100))
display_surface.blit(candy_crush, (90,230))

img3 = pygame.image.load('subway surfers.jpg')
subway_surfers = pygame.transform.scale(img3, (100,100))
display_surface.blit(subway_surfers, (90,370))

img4 = pygame.image.load('temple run.jpg')
temple_run = pygame.transform.scale(img4, (100,100))
display_surface.blit(temple_run, (90,510))

font = pygame.font.SysFont('arial', 36)

text = font.render('angry birds',True,(255,255,255))
text1 = font.render('candy crush',True,(255,255,255))
text2 = font.render('subway surfers',True,(255,255,255))
text3 = font.render('temple run',True,(255,255,255))
display_surface.blit(text,(350,100))
display_surface.blit(text1,(350,200))
display_surface.blit(text2,(350,300))
display_surface.blit(text3,(350,400))
pygame.display.update()
                     
running = True
while running:
    event = pygame.event.poll()
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
            pygame.quit()
    
    if event.type == pygame.MOUSEBUTTONDOWN:
        pos = pygame.mouse.get_pos()
        pygame.draw.circle(display_surface,
          (255,255,255) ,(pos), 20, 0)
        pygame.display.update()
    elif event.type == pygame.MOUSEBUTTONUP:
        pos2 = pygame.mouse.get_pos()
        pygame.draw.line(display_surface,(255,255,255), (pos), (pos2),5)
        pygame.draw.circle(display_surface,
          (255,255,255) ,(pos2), 20, 0)
        pygame.display.update()
        
