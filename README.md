# KShoot Game App
`NOTE:`: Pushing method to avoid enumerate stuck issues in Vscode Terminal: <br/> 
`git init .`<br/>
`git add .`<br/>
`git config --global http.postBuffer 157286400`<br/> 
`git commit -m "first commit"`<br/> 
`git remote add origin .GIT LINK OBTAINED FROM ABOVE`<br/> 
`git push -u origin main`<br/>
A classic Android-style shooting game using PyGame and Python. It is a classic arcade-styled game filled with 3 different enemies of varying speeds and sizes that give the player progressively more points as the games get more difficult. I created three game modes where the player can see how fast to clear the entire game in free play mode, then in accuracy mode where the player has limited ammo to get as many points as they possibly can. The highest scoring is tracked and saved in an external text file that the player can reset from the menu screen if they ever want to start over the game. The player will LEVEL UP to the higher levels if they get enough scores.
## ***[Copyright and Commercial Use Disclaimer](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/README.md#please-carefully-read-licensemd-about-the-open-source-restrictions-and-the-personal-use-policy-of-this-project-under-gpl-30-license-any-commericial-uses-on-this-project-by-other-than-the-owner-krystalzhang612-or-the-authorized-users-and-organizations-will-be-subjected-to-copyright-violation-with-sebsequent-legal-potential-concerns)***

⏬

### ***Please carefully read [LICENSE.md](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/LICENSE) about the Open Source restrictions and the personal use policy of this project under [GPL-3.0 license](https://www.gnu.org/licenses/gpl-3.0.en.html), any commericial uses on this project by other than the owner [@KrystalZhang612](https://github.com/KrystalZhang612) or the authorized users and organizations, will be subjected to copyright violation with sebsequent legal potential concerns.***
## KShoot Game App Overview:
<p align = "center">
  <img src = "https://user-images.githubusercontent.com/72481348/205469214-f4dd4aa8-a0d9-4c4e-a7a4-5422a839a147.mov">&nbsp;
  <img src = "https://user-images.githubusercontent.com/72481348/205469268-78a3443a-f744-45e2-b6dc-e247badacfaf.mov">&nbsp;
  <img src = "https://user-images.githubusercontent.com/72481348/205469289-9eee8139-a00a-482e-9a41-aeb92467c910.mov">&nbsp;
  <img src = "https://user-images.githubusercontent.com/72481348/205469306-5d566dbe-909d-40ed-a6d4-e7afc93d7fdf.mov">&nbsp; 
</p>


# Build
[Method to Run & Test the Project Locally](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/README.md#method-to-run--test-the-project-locally)<br/> 
[Prerequisites & Setups](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/README.md#prerequisites--setups)<br/> 
[Synchronous Developing Notes](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/README.md#synchronous-developing-notes)<br/> 
[Testing Result]()<br/> 
[Tags and Topics]()<br/>
# Contribution
[Author]()
# Compatiability
[Pygame does not require setup tools with even ctypes to install. Truly portable. Supports Linux (pygame comes with most main stream linux distributions), Windows (95, 98, ME, 2000, XP, Vista, 64-bit Windows, etc), Windows CE, BeOS, MacOS, Mac OS X, FreeBSD, NetBSD, OpenBSD, BSD/OS, Solaris, IRIX, and QNX.](https://www.pygame.org/wiki/about#:~:text=Pygame%20does%20not%20require%20setup,Solaris%2C%20IRIX%2C%20and%20QNX.)
# Method to Run & Test the Project Locally
### Download the entire project to local directory
### Use CMD or local Console to navigate to the local directory of the project folder.
### Run `python3 main.py runserver` to start running PyGame[macOS user]
### Run `python main.py runserver` to start running PyGame[Windows and Linux user]
### Start playing KShoot Game and level up! Resume, pause and accumulate high scores anytime! Have fun!
### CTRL+C to quit the game and terminate local server. 
# 🛠️ Developing Languages, Tools, and Techniques Needed
[Python 3](https://www.python.org/downloads/)<br/> 
[Vscode 1.73](https://code.visualstudio.com/)<br/> 
[PyGame](https://www.pygame.org/news)<br/> 
[pip](https://pypi.org/project/pip/)<br/>
<div>
  <img src = "https://github.com/devicons/devicon/blob/master/icons/python/python-original.svg" title = "Python" width = "60" height = "60"/>&nbsp;
  <img src = "https://github.com/devicons/devicon/blob/master/icons/vscode/vscode-original.svg" title = "Vscode" width = "60" height = "60"/>&nbsp;
  <img src = "https://github.com/KrystalZhang612/images-attachments-collection/blob/main/pygame%20logo.PNG"  title = "PyGame" width = "60" height = "60"/>&nbsp;
  
</div>

# Prerequisites & Setups
Upgrade pip in Vscode terminal:<br/> 
```bash
pip install --upgrade pip
```
Install PyGame with pip:
```bash
pip3 install pygame
```
# Synchronous Developing Notes
Import PyGame in [main.py](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/main.py):
```python3
import pygame
```
Initiate PyGame and import 3 levels of backgrounds so we got 3 levels of game backgrounds:<br/> 
[level1 background.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/level1%20background.PNG)<br/>
[level2 background.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/level2%20bakcground.PNG)<br/> 
[level3 background.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/level3%20background.PNG)<br/> 
Draw guns and different colors of lasers with various positions:
```python3
 def draw_gun():
    mouse_pos = pygame.mouse.get_pos()
    gun_point = (WIDTH / 2, HEIGHT - 200)
    lasers = ['red', 'purple', 'green']
    clicks = pygame.mouse.get_pressed()
    if mouse_pos[0] != gun_point[0]:
        slope = (mouse_pos[1] - gun_point[1]) / (mouse_pos[0] -
gun_point[0])
```
Adjust guns sizes to be smaller guns to be at center with better accuracy targeting objects:
```python3
guns.append(pygame.transform.scale(pygame.image.load(f'assets/guns/{i} .png'), (100, 100)))
```
[gun1.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/gun1.PNG)<br/> 
[gun2.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/gun2.PNG)<br/> 
[gun3.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/gun3.PNG)<br/>
Draw levels with coordinates and different targets and initialize enemies coordinates:<br/> 
[level1 birds.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/level1%20birds.PNG)<br/> 
[level2 bubbles.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/level2%20bubbles.PNG)<br/> 
[level3 alien spaceships.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/level3%20alien%20spaceships.PNG)<br/>
## ***Check shots:***
```python3
 def check_shot(targets, coords):
    global points
    mouse_pos = pygame.mouse.get_pos()
    for i in range(len(targets)):
        for j in range(len(targets[i])):
            if targets[i][j].collidepoint(mouse_pos):
                coords[i].pop(j)
                points += 10 + 10 * (i ** 2)
```
Now we can click the floating and moving targets to destroy them on board.
## ***Draw Score:***
```python3
 def draw_score():
    points_text = font.render(f'Points: {points}', True, 'black')
    screen.blit(points_text, (320, 660))
    shots_text = font.render(f'Total Shots: {total_shots}', True,
'black')
    screen.blit(shots_text, (320, 687))
    time_text = font.render(f'Time Elasped: {time_passed}', True,
'black')
    screen.blit(time_text, (320, 714))
    if mode == 0:
        mode_text = font.render(f'Freeplay!', True, 'black')
    if mode == 1:
        mode_text = font.render(f'Ammo Remaining: {ammo}', True,
'black')
    if mode == 2:
        mode_text = font.render(f'Time Remaining {time_remaining}',
True, 'black')
    screen.blit(mode_text, (320, 741))
```
[score drawed level1.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/score%20drawed%20level1.PNG)<br/> 
[score drawed level2.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/score%20drawed%20level2.PNG)<br/> 
[score drawed level3.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/score%20drawed%20level3.PNG)<br/>
## ***Menu control and setup:***
```python3
def draw_menu():
    global game_over, pause, mode, level, menu, time_passed,
total_shots, points, ammo
    global time_remaining, best_freeplay, best_ammo, best_timed,
write_values, clicked, new_coords
    game_over = False
    pause = False
```
[menu control bar showed.PNG](https://github.com/KrystalZhang612/KrystalZhang-KShoot-Game/blob/main/testing-result-kshoot-game-app/menu%20control%20bsr%20showed.PNG)<br/> 
Finally, Add pause, resume functionalities and background music in different levels.

# Testing Result



















