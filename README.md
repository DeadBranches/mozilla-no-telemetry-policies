# Disable Firefox Telemetry Programmatically

Firefox checks for a file called `policies.json` every time it starts. If present, Firefox applies the policies before any profile settings are loaded.

## Installation

### 1. Locate the `distribution` directory

`policies.json` must be placed in a directory called `distribution` inside the root directory of the Firefox profile you want the policies to apply to. The location of this directory varies by operating system.

#### On Windows

1. Visit `about:profiles` to find the relevant profile's **Root Directory**. If you're not sure which profile to use, look for *This is the profile in use*.
2. Inside the root directory, create the `distribution` directory if it doesn't already exist, then enter it.
```
   mkdir distribution
   cd distribution
```

#### On macOS

On macOS, `policies.json` must be placed inside `Firefox.app/Contents/Resources/distribution`.[^1]

> [!NOTE]
> `policies.json` is removed with each update.

```shell
cd /Applications/Firefox.app/Contents/Resources/
mkdir distribution
cd distribution
```

#### On Linux

On Linux, the location varies. To find it:

> Go to about:support, open the "Application Binary" folder ("Update Directory" in Nightly 78) to locate the profile root directory, and put `distribution` in there.[^2]

### 2. Install `policies.json`

Place `policies.json` into the `distribution` directory. You can either clone this repo or download the release.

   **Option 1:** Clone this repository
```shell
   cd distribution
   git clone git@github.com:DeadBranches/no-telemetry-policies.git .
```

   **Option 2:** Download the release
```shell
   cd distribution
   wget https://github.com/DeadBranches/mozilla-no-telemetry-policies/releases/latest/download/policies.json
```

---

[^1]: KevinHJ, (29 Nov, 2024). [*"Global policies.json equivalent for Macos"*](https://superuser.com/questions/1863144/global-policies-json-equivilent-for-macos)
[^2]: u/panoptigram, (21 May, 2021). [*"Where does policies.json go on Ubuntu 20.04"*](https://www.reddit.com/r/firefox/comments/gnv59x/comment/frbzy4r/)
