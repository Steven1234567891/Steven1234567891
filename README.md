from mcpi.minecraft import Minecraft
mc = Minecraft.create()

pos = mc.player.getPos()

x = pos.x
y = pos.y
z = pos.z



space = 0
while(mc.getBlock(x+space, y, z) != 66):
    #support cobblestone
    mc.setBlock(x+space, y-2, z-2, 4)
    mc.setBlock(x+space, y-2, z-1, 4)
    mc.setBlock(x+space, y-2, z, 4)
    mc.setBlock(x+space, y-2, z+1, 4)
    mc.setBlock(x+space, y-2, z+2, 4)

    #support gravel
    mc.setBlock(x+space, y-1, z-2, 13)
    mc.setBlock(x+space, y-1, z-1, 13)
    mc.setBlock(x+space, y-1, z, 13)
    mc.setBlock(x+space, y-1, z+1, 13)
    mc.setBlock(x+space, y-1, z+2, 13)

    #fencing
    mc.setBlock(x+space, y, z-2, 101)
    mc.setBlock(x+space, y, z+2, 101)

    #air level 1
    mc.setBlock(x+space, y+1, z-1, 0)
    mc.setBlock(x+space, y+1, z, 0)
    mc.setBlock(x+space, y+1, z+1, 0)

    #air level 2
    mc.setBlock(x+space, y+2, z-1, 0)
    mc.setBlock(x+space, y+2, z, 0)
    mc.setBlock(x+space, y+2, z+1, 0)

    #air level 3
    mc.setBlock(x+space, y+3, z-1, 0)
    mc.setBlock(x+space, y+3, z, 0)
    mc.setBlock(x+space, y+3, z+1, 0)

    if(space % 10 != 0):
        #track
        mc.setBlock(x+space, y, z-1, 0)
        mc.setBlock(x+space, y, z, 66)
        mc.setBlock(x+space, y, z+1, 0)
    else:
        #power track
        mc.setBlock(x+space, y, z-1, 0)
        mc.setBlock(x+space, y, z, 27)
        mc.setBlock(x+space, y, z+1, 76)

    if(space == 3):
        mc.spawnEntity(x+4,y,z, 42)
        
    space = space + 1

    
    print(space)
    pPos = mc.player.getPos()

x = pPos.x
y = pPos.y
z = pPos.z

#mc.setBlock(x, y, z+1, 89)
step = 0
while(step != 50):
    #gravel support
    mc.setBlock(x+step, y-2, z-1, 4)
    mc.setBlock(x+step, y-2, z, 4)
    mc.setBlock(x+step, y-2, z+1, 4)

    #gravel
    mc.setBlock(x+step, y-1, z-1, 13)
    mc.setBlock(x+step, y-1, z, 13)
    mc.setBlock(x+step, y-1, z+1, 13)

    if(step % 10 == 0):
        #rail
        mc.setBlock(x+step, y, z-1, 0)
        mc.setBlock(x+step, y, z, 0)
        mc.setBlock(x+step, y, z, 27)
        mc.setBlock(x+step, y, z+1, 76)
    else:
        #rail
        mc.setBlock(x+step, y, z-1, 0)
        mc.setBlock(x+step, y, z, 0)
        mc.setBlock(x+step, y, z, 66)
        mc.setBlock(x+step, y, z+1, 0)

    #air 1
    mc.setBlock(x+step, y+1, z-1, 0)
    mc.setBlock(x+step, y+1, z, 0)
    mc.setBlock(x+step, y+1, z+1, 0)

    #air 2
    mc.setBlock(x+step, y+2, z-1, 0)
    mc.setBlock(x+step, y+2, z, 0)
    mc.setBlock(x+step, y+2, z+1, 0)

    #air 3
    mc.setBlock(x+step, y+3, z-1, 0)
    mc.setBlock(x+step, y+3, z, 0)
    mc.setBlock(x+step, y+3, z+1, 0)

    #Tunnel1
    mc.setBlock(x+step, y, z-2, 5, 2)

    mc.setBlock(x+step, y, z+2, 5, 2)

    #Tunnel1
    mc.setBlock(x+step, y+1, z-2, 5, 5)

    mc.setBlock(x+step, y+1, z+2, 5, 5)

    #Tunnel2
    mc.setBlock(x+step, y+2, z-2, 22)

    mc.setBlock(x+step, y+2, z+2, 22)

    #Tunnel3
    mc.setBlock(x+step, y+3, z-2, 5, 5)
    
    mc.setBlock(x+step, y+3, z+2, 5, 5)

    #TunnelTop
    mc.setBlock(x+step, y+4, z-1, 22)
    mc.setBlock(x+step, y+4, z, 0)
    mc.setBlock(x+step, y+5, z, 89)
    mc.setBlock(x+step, y+4, z+1, 22)

    if(step == 0):
        mc.spawnEntity(x+4,y,z, 42)

    step = step + 1
