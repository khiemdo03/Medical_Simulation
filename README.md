# VR Medical Emergency Training Simulator

A comprehensive Virtual Reality training system for medical emergency procedures, built for Meta Quest headsets using Unity and Reallusion.

![Unity Version](https://img.shields.io/badge/Unity-2022.3%20LTS-blue)
![Platform](https://img.shields.io/badge/Platform-Meta%20Quest-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 🎯 Features

- **Realistic VR Training**: Immersive medical emergency scenarios in virtual reality
- **Hand Tracking**: Natural interactions using Meta Quest controllers
- **Performance Tracking**: Detailed scoring and feedback system
- **Multiple Scenarios**: Cardiac arrest, CPR, defibrillator usage
- **Audio Feedback**: Voice instructions and realistic medical sounds
- **Visual Guides**: Optional training mode with step-by-step guidance

## 📋 Prerequisites

### Software Requirements
- Unity 2022.3 LTS or newer
- Meta XR All-in-One SDK (v62.0+)
- Reallusion Character Creator 4 (optional)
- Reallusion iClone 8 (optional)
- Git
- Visual Studio 2022

### Hardware Requirements
- Meta Quest 2/3/Pro
- Development PC (Windows 10/11, 16GB+ RAM)
- USB-C cable for debugging

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/vr-medical-simulator.git
cd vr-medical-simulator
```

### 2. Open in Unity

1. Open Unity Hub
2. Click "Add" and select the cloned project folder
3. Open with Unity 2022.3 LTS

### 3. Install Dependencies

1. Open **Window > Package Manager**
2. Install Meta XR All-in-One SDK:
   - Click "+" > "Add package from git URL"
   - Enter: `com.meta.xr.sdk.all`
3. Install XR Interaction Toolkit:
   - Search for "XR Interaction Toolkit"
   - Click "Install"

### 4. Configure Build Settings

1. Go to **File > Build Settings**
2. Switch platform to **Android**
3. Click **Player Settings**
4. Set **Minimum API Level** to Android 10.0 (API 29)
5. Under **XR Plug-in Management**, enable **Oculus**

### 5. Connect Meta Quest

1. Enable **Developer Mode** on your Quest headset
2. Connect via USB-C cable
3. Allow USB debugging when prompted
4. In Unity, click **File > Build and Run**

## 📁 Project Structure

```
Assets/
├── Scenes/
│   └── MedicalSim.unity          # Main training scene
├── Scripts/
│   ├── Core/
│   │   ├── AudioManager.cs       # Audio system
│   │   ├── PerformanceTracker.cs # Scoring system
│   │   ├── PatientVitals.cs      # Patient simulation
│   │   ├── VFXManager.cs         # Visual effects
│   │   └── VRHandController.cs   # VR input handling
│   ├── Interactions/
│   │   ├── CPRController.cs      # CPR mechanics
│   │   ├── Defibrillator.cs      # Defibrillator system
│   │   └── GrabbableObject.cs    # VR object interaction
│   ├── Scenarios/
│   │   ├── CardiacArrestScenario.cs
│   │   └── TrainingMode.cs       # Guided training
│   └── UI/
│       └── UIManager.cs          # UI management
├── Prefabs/
│   ├── Characters/               # Patient models
│   ├── Environments/             # Hospital room
│   └── MedicalEquipment/         # Interactive medical tools
├── Materials/
├── Audio/
└── Resources/
```

## 🎮 How to Play

### Controls (Meta Quest)

- **Grip Button**: Grab objects
- **Trigger**: Activate/use equipment
- **Thumbstick**: Movement (if enabled)
- **Menu Button**: Pause game

### Training Scenario: Cardiac Arrest

1. **Start** - Observe the patient in cardiac arrest
2. **Grab Paddles** - Pick up both defibrillator paddles
3. **Position** - Place paddles correctly on patient's chest
4. **Charge** - Hold in position for 2 seconds
5. **Shock** - Deliver shock (automatic when charged)
6. **Repeat** - Perform 3 successful shocks
7. **Complete** - Patient stabilized!

### Scoring System

- Paddle Grabbed: 50 points
- Correct Placement: 100 points each
- Shock Delivered: 150 points each
- Procedure Complete: 300 points
- Time Bonus: Up to 200 points
- Accuracy Bonus: Up to 300 points

**Maximum Score**: 1000 points

## 🛠️ Development

### Adding New Scenarios

1. Create new script in `Assets/Scripts/Scenarios/`
2. Inherit from `MonoBehaviour`
3. Reference `PerformanceTracker` for scoring
4. Use `AudioManager` for audio feedback
5. Update `UIManager` for instructions

### Customizing Patient Models

1. Create character in Reallusion Character Creator 4
2. Export to Unity using Auto-Setup plugin
3. Replace patient GameObject in scene
4. Adjust `PatientVitals` script references

### Adding Audio

1. Place audio files in `Assets/Audio/`
2. Add clips to `AudioManager` in Inspector
3. Call `AudioManager.Instance.PlaySFX(clip)`

## 🧪 Testing

### In Unity Editor
- Press Play to test in Game view
- Use XR Device Simulator for testing without headset

### On Device
1. Build and Run to Quest
2. Check console logs via `adb logcat`
3. Test all interactions thoroughly

## 📊 Performance Optimization

- Keep draw calls under 1000
- Target 72 FPS minimum (Quest 2) or 90 FPS (Quest 3)
- Use object pooling for particles
- Optimize textures (2048x2048 max)
- Use occlusion culling

## 🐛 Troubleshooting

### Build Fails
- Ensure Android SDK and NDK are installed
- Check minimum API level is set to 29
- Verify Oculus XR Plugin is enabled

### VR Not Working
- Enable Developer Mode on Quest
- Install Meta Quest Developer Hub
- Check USB connection and drivers

### Performance Issues
- Reduce texture quality in Quality Settings
- Disable shadows if needed
- Lower particle system max particles

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/NewScenario`)
3. Commit changes (`git commit -m 'Add new scenario'`)
4. Push to branch (`git push origin feature/NewScenario`)
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License - see LICENSE file for details.

## 🙏 Acknowledgments

- Unity Technologies for XR Interaction Toolkit
- Meta for Quest SDK
- Reallusion for character creation tools
- Medical advisors for scenario accuracy

## 📧 Contact

- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your.email@example.com
- Discord: YourDiscord#0000

## 🔗 Links

- [Unity Documentation](https://docs.unity3d.com/)
- [Meta XR SDK](https://developer.oculus.com/documentation/unity/)
- [Reallusion Unity Auto-Setup](https://www.reallusion.com/character-creator/auto-setup.html)

---

**Built with ❤️ for medical training education**
