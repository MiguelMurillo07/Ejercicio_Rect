# Ejercicio_Rect
ejercicio rect



import pygame
import sys

# Inicializa pygame
pygame.init()

# Configuraciones de la ventana
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Mover un Rectángulo con el Cursor")

# Colores
black = (0, 0, 0)
red = (255, 0, 0)

# Dimensiones del rectángulo
rect_width = 100
rect_height = 100

# Bucle principal del juego
running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Obtiene la posición del cursor
    mouse_x, mouse_y = pygame.mouse.get_pos()

    # Calcula la posición del rectángulo centrado en el cursor
    rect_x = mouse_x - rect_width // 2
    rect_y = mouse_y - rect_height // 2

    # Limpia la pantalla
    screen.fill(black)

    # Dibuja el rectángulo
    pygame.draw.rect(screen, red, (rect_x, rect_y, rect_width, rect_height))

    # Actualiza la pantalla
    pygame.display.flip()

    # Controla la velocidad del bucle
    pygame.time.Clock().tick(60)

# Sale de pygame
pygame.quit()
sys.exit()
