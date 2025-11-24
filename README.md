# AI-Powered Ring Security Camera Monitor

![GitHub stars](https://img.shields.io/github/stars/LunaticKrave/ha-ring-ai-security-monitor?style=social)
![GitHub forks](https://img.shields.io/github/forks/LunaticKrave/ha-ring-ai-security-monitor?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/LunaticKrave/ha-ring-ai-security-monitor?style=social)
![GitHub last commit](https://img.shields.io/github/last-commit/LunaticKrave/ha-ring-ai-security-monitor)
![GitHub issues](https://img.shields.io/github/issues/LunaticKrave/ha-ring-ai-security-monitor)

AI-powered security camera monitoring for Home Assistant using Ring (or any camera brand) with GPT-4o-mini vision analysis and smart notifications.

## Overview

This Home Assistant automation transforms your basic motion detection into an intelligent security system. When motion is detected on your Ring cameras (or any compatible camera brand like Nest, Arlo, Reolink, Unifi, etc.), it captures snapshots from multiple angles and uses GPT-4o-mini's vision capabilities to analyze what actually triggered the alert.

No more false alarms about tree branches! Get smart, contextual descriptions like:
- "Amazon delivery driver dropped off a package at the front door"
- "A gray cat is exploring the side yard"
- "UPS truck passing by on the street"
- "Person in dark hoodie lingering near the front door - appears suspicious"

## Features

- 🤖 **AI Vision Analysis** - GPT-4o-mini analyzes camera snapshots to describe what's happening
- 📸 **Multi-Camera Support** - Combines views from multiple cameras for comprehensive coverage
- 📱 **Smart Notifications** - Mobile notifications with AI-generated descriptions and images
- 🔊 **Voice Announcements** - Optional voice alerts via Home Assistant satellites (daytime only)
- 🎯 **Context-Aware** - Distinguishes between deliveries, animals, vehicles, people, and suspicious activity
- 🔔 **Multiple Alert Methods** - Mobile push, persistent notifications, and voice announcements
- ⚡ **Real-Time** - Processes motion events within seconds
- 🌐 **Camera Agnostic** - Works with Ring, Nest, Arlo, Reolink, Unifi, Wyze, or any camera with Home Assistant integration

## Requirements

### Integrations

1. **LLM Vision Integration** (HACS)
   - Install from HACS: [LLM Vision](https://github.com/valentinfrlch/ha-llmvision)
   - Provides the `llmvision.image_analyzer` service
   - Supports multiple vision models (OpenAI, Google, Anthropic, etc.)

2. **OpenAI API Access**
   - GPT-4o-mini API key configured
   - Cost: ~$0.002 per analysis (very affordable!)
   - Alternative: Can use other vision models supported by LLM Vision

3. **Camera Integration**
   - Ring (via Ring integration)
   - Nest (via Google Nest integration)
   - Arlo, Reolink, Unifi, Wyze, etc.
   - Must support `camera.snapshot` service
   - Must have motion detection sensors

4. **Mobile App** (optional but recommended)
   - Home Assistant mobile app for push notifications
   - iOS or Android

5. **Voice Assistant** (optional)
   - Home Assistant voice satellite or media player
   - For spoken announcements during daytime hours

### Entities Required

- Motion sensor entities (e.g., `binary_sensor.front_door_motion`)
- Camera snapshot entities (e.g., `camera.front_door_snapshot`)
- LLM Vision provider configured
- Notification service (e.g., `notify.mobile_app_iphone`)

## Installation

### 1. Install Prerequisites

**Install LLM Vision via HACS:**
1. Open HACS in Home Assistant
2. Search for "LLM Vision"
3. Install the integration
4. Restart Home Assistant

**Configure LLM Vision:**
1. Go to Settings → Devices & Services → Add Integration
2. Search for "LLM Vision"
3. Add your OpenAI API key
4. Select GPT-4o-mini as your model
5. Note the provider ID for configuration

### 2. Create Required Directories

Ensure the snapshot directory exists:
```bas hmkdir -p /config/www/tmp
# AI-Powered Ring Security Camera Monitor

![GitHub stars](https://img.shields.io/github/stars/LunaticKrave/ha-ring-ai-security-monitor?style=social)
![GitHub forks](https://img.shields.io/github/forks/LunaticKrave/ha-ring-ai-security-monitor?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/LunaticKrave/ha-ring-ai-security-monitor?style=social)
![GitHub last commit](https://img.shields.io/github/last-commit/LunaticKrave/ha-ring-ai-security-monitor)
![GitHub issues](https://img.shields.io/github/issues/LunaticKrave/ha-ring-ai-security-monitor)

AI-powered security camera monitoring for Home Assistant using Ring (or any camera brand) with GPT-4o-mini vision analysis and smart notifications.

## Overview

This Home Assistant automation transforms your basic motion detection into an intelligent security system. When motion is detected on your Ring cameras (or any compatible camera brand like Nest, Arlo, Reolink, Unifi, etc.), it captures snapshots from multiple angles and uses GPT-4o-mini's vision capabilities to analyze what actually triggered the alert.

No more false alarms about tree branches! Get smart, contextual descriptions like:
- "Amazon delivery driver dropped off a package at the front door"
- "A gray cat is exploring the side yard"
- "UPS truck passing by on the street"
- "Person in dark hoodie lingering near the front door - appears suspicious"

## Features

- 🤖 **AI Vision Analysis** - GPT-4o-mini analyzes camera snapshots to describe what's happening
- 📸 **Multi-Camera Support** - Combines views from multiple cameras for comprehensive coverage
- 📱 **Smart Notifications** - Mobile notifications with AI-generated descriptions and images
- 🔊 **Voice Announcements** - Optional voice alerts via Home Assistant satellites (daytime only)
- 🎯 **Context-Aware** - Distinguishes between deliveries, animals, vehicles, people, and suspicious activity
- 🔔 **Multiple Alert Methods** - Mobile push, persistent notifications, and voice announcements
- ⚡ **Real-Time** - Processes motion events within seconds
- 🌐 **Camera Agnostic** - Works with Ring, Nest, Arlo, Reolink, Unifi, Wyze, or any camera with Home Assistant integration

## Requirements

### Integrations

1. **LLM Vision Integration** (HACS)
   - Install from HACS: [LLM Vision](https://github.com/valentinfrlch/ha-llmvision)
   - Provides the `llmvision.image_analyzer` service
   - Supports multiple vision models (OpenAI, Google, Anthropic, etc.)

2. **OpenAI API Access**
   - GPT-4o-mini API key configured
   - Cost: ~$0.002 per analysis (very affordable!)
   - Alternative: Can use other vision models supported by LLM Vision

3. **Camera Integration**
   - Ring (via Ring integration)
   - Nest (via Google Nest integration)
   - Arlo, Reolink, Unifi, Wyze, etc.
   - Must support `camera.snapshot` service
   - Must have motion detection sensors

4. **Mobile App** (optional but recommended)
   - Home Assistant mobile app for push notifications
   - iOS or Android

5. **Voice Assistant** (optional)
   - Home Assistant voice satellite or media player
   - For spoken announcements during daytime hours

### Entities Required

- Motion sensor entities (e.g., `binary_sensor.front_door_motion`)
- Camera snapshot entities (e.g., `camera.front_door_snapshot`)
- LLM Vision provider configured
- Notification service (e.g., `notify.mobile_app_iphone`)

## Installation

### 1. Install Prerequisites

**Install LLM Vision via HACS:**
1. Open HACS in Home Assistant
2. Search for "LLM Vision"
3. Install the integration
4. Restart Home Assistant

**Configure LLM Vision:**
1. Go to Settings → Devices & Services → Add Integration
2. Search for "LLM Vision"
3. Add your OpenAI API key
4. Select GPT-4o-mini as your model
5. Note the provider ID for configuration

### 2. Create Required Directories

Ensure the snapshot directory exists:
```bash
mkdir -p /config/www/tmp
```

### 3. Download and Configure

1. **Clone or download this repository**

2. **Copy the YAML file** to your Home Assistant automations

3. **Edit the configuration** (see Configuration section below)

4. **Reload automations** in Home Assistant

5. **Test** by triggering motion or manually running the automation

## Configuration

Open `ai-camera-motion-analysis.yaml` and update the following:

### Required Changes

| Setting | Line(s) | What to Change |
|---------|---------|----------------|
| Motion Sensors | ~7, ~11 | Replace with your camera motion sensor entities |
| Camera Entities | ~22, ~28 | Replace with your camera snapshot entities |
| LLM Provider ID | ~53 | Replace with your LLM Vision provider ID |
| Notification Service | ~59 | Replace with your mobile notify service |
| Home Assistant URL | ~65, ~67, ~74 | Replace with your HA IP or domain |
| Voice Device ID | ~81, ~87 | Replace with your voice satellite device ID (optional) |

### Finding Your LLM Provider ID

1. Go to **Settings** → **Integrations**
2. Find **LLM Vision**
3. Click on it and look for the provider ID
4. It will look like: `01JYA7ZFQ0THX6863Y01TSY5WY`

### Finding Your Camera Entities

1. Go to **Developer Tools** → **States**
2. Search for your camera names
3. Look for entities like:
   - `camera.front_door_snapshot`
   - `binary_sensor.front_door_motion`

### Setting Up File Paths

The automation saves snapshots to `/config/www/tmp/`. This makes them accessible via:
- Local URLs: `http://YOUR_IP:8123/local/tmp/frontdoorcamera.jpg`
- Mobile notifications: Images attach to push notifications
- Persistent notifications: Clickable links in HA interface

**Important:** Make sure your Home Assistant URL is accessible from your mobile device!

### Optional Customization

| Setting | Line(s) | Default | Description |
|---------|---------|---------|-------------|
| Snapshot Delay | ~17 | 2 seconds | Wait time before capturing snapshots |
| Voice Hours | ~78 | 8am-10pm | When voice announcements are active |
| Max Tokens | ~41 | 150 | Length of AI response |
| Temperature | ~42 | 0.2 | AI creativity (lower = more factual) |
| Image Width | ~40 | 1280px | Snapshot resolution for analysis |
| Voice Volume | ~83 | 0.7 (70%) | Volume level for announcements |

## How It Works

1. **Motion Detected**: Motion sensor triggers (front door or side yard)
2. **Snapshot Capture**: Waits 2 seconds, then captures images from both cameras
3. **AI Analysis**: Sends both images to GPT-4o-mini with instructions to analyze the scene
4. **Notification Generation**: Creates a unified description of what's happening
5. **Alert Delivery**:
   - Mobile push notification with images
   - Persistent notification in HA interface
   - Voice announcement (if during daytime hours)
6. **Single Mode**: Won't trigger again until current analysis completes

## Example Notifications

### Delivery
> "Motion detected: Amazon delivery driver in blue uniform just dropped off a package at the front door and is heading back to their truck."

### Animal
> "Motion detected: A gray tabby cat is prowling around the side yard near the fence, probably hunting."

### Vehicle
> "Motion detected: FedEx truck passing by on the street, driver didn't stop at the house."

### Suspicious Activity
> "Motion detected: Person in dark hoodie lingering near the front door, looking around nervously. They haven't knocked or approached the door directly."

### False Alarm
> "Motion detected: No people or vehicles visible. Likely triggered by wind moving the plants near the camera."

## Customizing the AI Prompt

The AI prompt (around line 44) can be customized to change how descriptions are generated:

**Current prompt emphasizes:**
- Unified description from multiple camera views
- People descriptions (appearance, clothing, activity)
- Vehicle identification (type, purpose)
- Animal detection
- Suspicious behavior flags
- Package detection
- Conversational, friendly tone

**You can modify it to:**
- Focus more on security threats
- Provide more/less detail
- Change the tone (professional vs casual)
- Add specific things to look for
- Adjust character length

## Multi-Camera Setup

This automation is designed for 2 cameras but can be easily adapted:

**For more cameras:**
1. Add additional snapshot actions (copy lines 24-29)
2. Add camera entities to the `image_entity` list (line 54-56)
3. Update filenames and URLs throughout

**For a single camera:**
1. Remove one of the snapshot actions
2. Remove one camera from `image_entity` list
3. Update prompt to reference single view
4. Update notification URLs

## Cost Considerations

GPT-4o-mini vision analysis is very affordable:
- ~$0.002 per analysis (2 images)
- 10 motion events per day = ~$0.60/month
- 50 motion events per day = ~$3.00/month

For comparison, many dedicated AI camera services charge $5-30/month per camera!

## Troubleshooting

### No notifications arriving

- Check that motion sensors are working (Developer Tools → States)
- Verify LLM Vision integration is configured
- Check Home Assistant logs for errors
- Test notification service manually

### AI analysis fails

- Verify your OpenAI API key is valid and has credits
- Check LLM Vision integration status
- Look for error messages in persistent notifications
- Ensure snapshot files are being created in `/config/www/tmp/`

### Images not appearing in notifications

- Verify your Home Assistant URL is accessible from your phone
- Check that snapshot files exist in `/config/www/tmp/`
- Try accessing the URL directly in a browser
- For iOS: May need to use HTTPS with valid certificate

### Voice announcements not working

- Verify device ID is correct
- Check voice satellite is online
- Test volume manually
- Confirm time is within 8am-10pm window

### Analysis is too slow

- Reduce `target_width` (line ~40) to 800 or 640
- Reduce `max_tokens` (line ~41) to 100
- Check your internet speed

### False positives

- Adjust motion sensor sensitivity in camera settings
- Add conditions to filter specific times/modes
- Modify AI prompt to ignore certain triggers

## Advanced Customization

### Adding Presence Detection

Only notify when you're away:
```yaml
conditions:
  - condition: state
    entity_id: person.your_name
    state: "not_home"
```

### Different Notifications for Different Times

Night mode with different prompt:
```yaml
- if:
    - condition: time
      after: "22:00:00"
      before: "06:00:00"
  then:
    # Use more security-focused prompt for night
```

### Integration with Security System

Only analyze when alarm is armed:
```yaml
conditions:
  - condition: state
    entity_id: alarm_control_panel.home
    state: "armed_away"
```

### Saving Notable Events

Log suspicious activity to a file or database for review.

## Privacy Considerations

- **Images are processed** by OpenAI's GPT-4o-mini vision API
- **Snapshots are stored locally** in your Home Assistant instance
- **No cloud storage** of images (beyond API processing)
- **Review OpenAI's privacy policy** for their data retention
- Consider using a self-hosted vision model for complete privacy

## Compatible Camera Brands

This automation works with any camera that has:
1. Home Assistant integration
2. Motion detection sensor
3. Snapshot capability

**Tested/Compatible brands:**
- Ring (Doorbells, Stick Up Cams, Floodlight Cams)
- Nest (Nest Cam, Nest Hello)
- Arlo (Pro, Ultra, Essential)
- Reolink (All models with HA integration)
- Unifi Protect cameras
- Wyze (via RTSP or integration)
- Amcrest cameras
- Hikvision cameras
- Dahua cameras
- Generic RTSP/ONVIF cameras

## Contributing

Contributions are welcome! Feel free to:
- Report bugs or issues
- Suggest prompt improvements
- Share your customizations
- Submit pull requests
- Add support for additional notification methods

## Future Enhancements

Ideas for future development:
- Face recognition integration
- Object tracking across multiple cameras
- Automatic video clip generation
- Integration with NVR systems
- Custom alerting based on object types
- Historical analysis and reporting

## License

This project is open source and available under the MIT License.

## Acknowledgments

- [LLM Vision](https://github.com/valentinfrlch/ha-llmvision) integration by valentinfrlch
- OpenAI for GPT-4o-mini vision capabilities
- Home Assistant community
- Ring, Nest, and other camera manufacturers

## Support

If you find this automation useful, please star the repository! ⭐

For issues, questions, or feature requests, please open an issue on GitHub.

## Related Projects

- [FlightRadar24 Low-Flying Plane Announcer](https://github.com/LunaticKrave/ha-flightradar24-announcer) - Another AI-powered HA automation

---

**Note**: This automation requires an active internet connection and API access. Analysis quality depends on camera image quality, lighting conditions, and API response times. Actual costs may vary based on usage.
