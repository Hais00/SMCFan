
# SMCFan CLI

SMCFan CLI is a command-line tool for managing and monitoring the speed and mode of system fans. It allows users to list available fans, set their speed, or adjust their operating mode.

## Features

- **List Fans**: View all fans with their current speeds, minimum/maximum speeds, and operating modes.
- **Set Fan Mode**: Switch between `automatic` or `forced` mode for a specified fan.
- **Set Fan Speed**: Define a target speed (in RPM) for a fan when in `forced` mode.
- **Help**: Display a guide on how to use the CLI.

---

## Installation

1. Download the `SMCFan` binary file from the repository or release page.
2. Place the binary in a directory included in your system's PATH, or run it directly from its location.

---

## Usage

### General Command Syntax

```bash
SMCFan [OPTIONS]
```

### Options

- `--fan`, `-f [ID]`: Specify the ID of the fan you want to manage.
- `--mode`, `-m [automatic|forced]`: Set the fan's operating mode.
- `--speed`, `-s [RPM]`: Define the target speed for the fan in RPM.
- `--list`, `-l`: List all fans along with their current information.
- `--help`, `-h`: Display the help guide.

---

### Examples

#### List All Fans

```bash
SMCFan --list
```

**Output example:**
```
ID  Current Speed   Min Speed   Max Speed   Mode
0   1200 RPM        800 RPM     2000 RPM    automatic
1   1500 RPM        900 RPM     2500 RPM    forced
```

#### Set Fan to Automatic Mode

```bash
SMCFan --fan 0 --mode automatic
```

**Output:**
```
Fan 0 mode set to automatic.
```

#### Set Fan Speed

```bash
SMCFan --fan 1 --speed 1800
```

**Output:**
```
Fan 1 speed set to 1800 RPM.
```

#### Display Help

```bash
SMCFan --help
```

---

## Error Handling

The application provides detailed error messages for incorrect or incomplete inputs:

- Invalid arguments: `Unrecognized argument: [argument]`
- Missing required arguments: `Specify the fan ID with --fan or -f.`
- Invalid fan ID: `Invalid fan ID: [ID]`
- Invalid speed: `Speed must be between [MinSpeed] and [MaxSpeed] RPM.`
- Invalid mode: `Invalid mode: [mode]. Use 'automatic' or 'forced'.`

---

## License

This project is licensed under the [MIT License](LICENSE).
