# Rust-City-Builder
A city builder made in Rust to simulate the creation of streets with addresses.

Author: Timothy Johnson <br>
Date: May 2024

## Overview

&nbsp;&nbsp;&nbsp;&nbsp;A city-building simulation written in Rust, focused on the procedural generation of streets and mapping addresses.
Inspired by real-world urban layouts—such as Olympia, WA—this lightweight terminal tool models city grids, assigns addresses to intersections, and visualizes road infrastructure via a grid-based ASCII map.

&nbsp;&nbsp;&nbsp;&nbsp;Rust-City-Builder is a command-line simulation that mimics the layout of a simple urban grid by randomly generating North-South and East-West roads.
It assigns address names based on pre-defined sources (like Olympia street names) and maps them to a 2D grid, rendering it with basic ASCII visualization.

Designed for experimenting with procedural content generation in Rust.

🧩 Features

    🛣️ Randomly generates vertical and horizontal roads

    🗺️ Displays a grid-based map of the city with roads (#), intersections (o), and empty land (.)

    🏙️ Assigns street names and address strings to map coordinates

    🔁 Modular architecture for city drawing, address management, and name reading

    📦 Olympia-specific address data sourced from real geographic datasets

🔄 User Workflow

    Run the program with cargo run

    Watch as streets are generated and visualized in the terminal

    View a sample of assigned addresses printed with coordinate keys

    Extend or modify the city builder using alternate name sets or additional logic

📁 Code Structure

.<br>
Rust-City-Builder/<br>
├── src/<br>
│   ├── addresser/<br>
│   │   ├── mod.rs<br>
│   │   ├── olympia.rs &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Olympia-specific street name logic<br>
│   │   └── tokyo.rs &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; (Stub for alternate future address schemes)<br>
│   ├── city_drawer.rs &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Grid drawing and road layout logic<br>
│   ├── name_reader.rs &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Street name parsing from files<br>
│   ├── lib.rs<br>
│   └── main.rs &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Simulation entry point<br>
├── street-names.txt &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; List of street names<br>
├── city-map.txt &nbsp;&nbsp;&nbsp;---&nbsp;&nbsp;&nbsp; Output visualizations<br>
├── Cargo.toml<br>
├── Cargo.lock<br>

⚙️ How It Works

🧱 In-Memory Grid

    The city is modeled as a 2D array: [['.'; BOUND]; BOUND]

    Roads (#) are laid in the grid at randomly spaced intervals

    Intersections (o) are marked adjacent to roads

🚗 Road Generator

    gen_random_roads() creates vertical and horizontal roads at randomized intervals

    Road direction: RoadDirection::NorthSouth or RoadDirection::EastWest

🏡 Address Mapping

    AddressesMap (HashMap<(usize, usize), String>) stores generated address labels per coordinate

    Olympia street names are assigned from street-names.txt

🖼️ City Drawer

    city_drawer() maps all roads to the grid

    Connected intersections are marked

    Results are printed as ASCII art in terminal

🖼️ Screenshots / Visuals

![citybuilderbanner](https://github.com/user-attachments/assets/9f76d898-4036-487b-8d5d-204823acfdaf)

Hello, city!<br>
Added Road { coord: 6, direction: NorthSouth }<br>
Added Road { coord: 13, direction: NorthSouth }<br>
...<br>
The number of generated addresses is 137<br>
The address at coordinates (6, 8) is Martin Way E & Eastside St SE<br>
The address at coordinates (13, 12) is Pacific Ave SE & Plum St SE<br>
<br>
Grid Output:<br>
.....o#o..........................................<br>
.....o#o..........................................<br>
.....o#o..........................................<br>
.....o#o..........................................<br>
.....o#o..........................................<br>
oooooo#ooooooooooooooooooooooooooooooooooooooooooo<br>
##################################################<br>
oooooo#ooooooooooooooooooooooooooooooooooooooooooo<br>
.....o#o..........................................<br>

🧰 Technologies Used

    🦀 Rust	Core programming language
    
    📦 Cargo	Build system and package manager for Rust
    
    📚 std::collections::HashMap	Efficient address map storage
    
    🎲 rand crate	Random number generation for procedural layouts
    
    📄 File I/O	Parses real-world street names from text files

🚀 Getting Started

    To clone and run this project locally:

      git clone https://github.com/MrTimmyJ/Rust-City-Builder.git
      cd Rust-City-Builder
      cargo run

      ⚠️ Requires Rust and Cargo installed 

  Get [Rust](https://www.rust-lang.org/tools/install)

🌱 Upcoming Features

    💾 Save generated maps to file

    🗂️ Switch between address schemes (Olympia, Tokyo, etc.)

    🏙️ Add buildings, zoning, and population simulation

    📏 Customizable city size and road density

    🧠 Smarter intersection logic for address naming

📎 External Reference

Street names from:
https://geographic.org/streetview/usa/wa/thurston/olympia.html

🪪 License

This open-source project is available under the [MIT License](https://opensource.org/license/mit).
