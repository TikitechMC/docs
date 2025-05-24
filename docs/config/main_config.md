# ⚙️ Main Settings

## 🐁 Cursor
The cursor has three possible modes, two of which having some small drawbacks and a mode that automatically chooses the perfect cursor based on the user's environment.

### 🐴 Clientsided cursor
This cursor type instantly moves when you move your mouse, it is based on a horse and uses core resource pack shaders. It sadly does this by removing a horse marking or the zombie horse texture, this will be redone in the future. Serversided rendering like hover will still be ping-based and updates accordingly, desync thus isn't uncommon.

### 💻 Serversided cursor
The serversided cursor type uses an entity that moves based on the rotation by the player, this means it has latency equal to around double your ping because of the two way messaging. Sunscreen adds some interpolation to smooth out the delay and kinks caused by this cursor method.

### 🪄 Automatic mode
Automatice mode, like the name suggests, chooses either one of the cursor types described above based on ping and other factors. Auto mode always starts in client sided mode but might move to serversided if it notices low ping (under 10) for a prolonged period of time.