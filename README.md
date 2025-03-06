---

# **SimpleTerrain API**![Terrain](https://github.com/user-attachments/assets/4292ae68-507a-44a6-86f0-8952b1ac40be)

A lightweight and efficient API for saving, loading, and managing terrain as a folder-based storage system in Roblox.

---

## **Table of Contents**
- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
  - [Save Terrain](#save-terrain)
  - [Load Terrain](#load-terrain)
  - [Unload Terrain](#unload-terrain)
  - [Update Terrain](#update-terrain)
- [Functions](#functions)
  - [SaveTerrain](#saveterrain)
  - [LoadTerrain](#loadterrain)
  - [UnloadTerrain](#unloadterrain)
  - [UpdateTerrain](#updateterrain)

---

## **Overview**

**SimpleTerrain** is an easy-to-use API designed to save, load, and manipulate terrain regions within Roblox games. By breaking down terrain into manageable chunks, this API allows for efficient storage and retrieval of terrain data. Terrain is saved as a folder containing serialized chunks and metadata, making it simple to update, remove, and reload terrain regions dynamically.

---

## **Installation**

To use this API in your project:

1. Get the API from the ROBLOX Marketplace.

- **[Get Simple Terrain API](https://create.roblox.com/store/asset/113792664371880/)**  

2. **Import the API** into your game by copying the script into **ReplicatedStorage**, **ServerStorage**, or any other location appropriate for your needs.

```lua
local SimpleTerrain = require(game.ReplicatedStorage.SimpleTerrain)  -- Example path
```

---

## **Usage**

### **Save Terrain**

To save a specific region of terrain, use the `SaveTerrain` function. This will serialize the terrain data into manageable chunks and save it in a folder.

```lua
local folder, message = SimpleTerrain:SaveTerrain(name, parent, removeOnSave, size, position)
print(message)
```

#### **Parameters**
- `name` *(string)* – The name for the saved terrain folder.
- `parent` *(Instance)* – The parent where the terrain data will be stored (e.g., `ReplicatedStorage` or `ServerStorage`).
- `removeOnSave` *(boolean)* – If `true`, the terrain will be cleared after saving.
- `size` *(Vector3)* – The size of the terrain region to save.
- `position` *(Vector3)* – The position of the terrain region.

#### **Returns**
- `folder` *(Folder)* – The folder containing the saved terrain chunks.
- `message` *(string)* – A confirmation message.

---

### **Load Terrain**

To load a previously saved terrain region, use the `LoadTerrain` function. This will reconstruct the terrain from the saved chunks and apply it back into the world.

```lua
local message = SimpleTerrain:LoadTerrain(folder)
print(message)
```

#### **Parameters**
- `folder` *(Folder)* – The folder containing the saved terrain data, including chunked data and metadata.

#### **Returns**
- `message` *(string)* – A success or error message.

---

### **Unload Terrain**

To unload a previously loaded terrain region, use the `UnloadTerrain` function. This will remove all terrain data in the specified region and reset it to air.

```lua
local message = SimpleTerrain:UnloadTerrain(folder)
print(message)
```

#### **Parameters**
- `folder` *(Folder)* – The folder containing the terrain data to be unloaded.

#### **Returns**
- `message` *(string)* – A confirmation message.

---

### **Update Terrain**

To modify the terrain region’s size or position, use the `UpdateTerrain` function. This will update the terrain with new data and re-save it.

```lua
local message = SimpleTerrain:UpdateTerrain(folder, size, position)
print(message)
```

#### **Parameters**
- `folder` *(Folder)* – The folder containing the saved terrain data to update.
- `size` *(Vector3)* – The new size of the terrain region.
- `position` *(Vector3)* – The new position of the terrain region.

#### **Returns**
- `message` *(string)* – A confirmation message.

---

## **Functions**

### **SaveTerrain**

```lua
SimpleTerrain:SaveTerrain(name, parent, removeOnSave, size, position)
```
- **name** *(string)* – The name of the terrain.
- **parent** *(Instance)* – The parent instance where the terrain folder will be stored.
- **removeOnSave** *(boolean)* – If true, clears the terrain after saving.
- **size** *(Vector3)* – The size of the region to save.
- **position** *(Vector3)* – The position where the terrain is located.

**Returns:** `(Folder, string)` – A folder containing terrain data and a success message.

---

### **LoadTerrain**

```lua
SimpleTerrain:LoadTerrain(folder)
```
- **folder** *(Folder)* – The folder containing the terrain data.

**Returns:** `(string)` – A success or error message.

---

### **UnloadTerrain**

```lua
SimpleTerrain:UnloadTerrain(folder)
```
- **folder** *(Folder)* – The folder containing the terrain data.

**Returns:** `(string)` – A success message.

---

### **UpdateTerrain**

```lua
SimpleTerrain:UpdateTerrain(folder, size, position)
```
- **folder** *(Folder)* – The folder containing the saved terrain data.
- **size** *(Vector3)* – The new size of the terrain region.
- **position** *(Vector3)* – The new position of the terrain region.

**Returns:** `(string)` – A success message.

---
