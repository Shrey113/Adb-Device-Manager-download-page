graph TD
  subgraph Android Device
    A1[ADB Daemon]
    A2[Custom Android App]
  end

  subgraph Windows Application
    W1[ADB Client\n(Screen Mirroring + Control)]
    W2[Non-ADB Socket/HTTP Listener]
    W3[Unified GUI]
  end

  %% ADB Communication
  A1 -->|ADB| W1
  W1 --> W3

  %% Non-ADB Communication
  A2 -->|Real-time Events\n(Call, Notifications, Media)| W2
  W2 --> W3

  %% ADB Features
  subgraph "ADB Capabilities"
    C1[Screen Mirroring with Control]
    C2[Keyboard & Mouse Input]
    C3[Audio Streaming]
    C4[Launch/Manage Apps]
    C5[Virtual Display Control]
  end
  W1 --> C1
  W1 --> C2
  W1 --> C3
  W1 --> C4
  W1 --> C5

  %% Non-ADB Features
  subgraph "Non-ADB Capabilities"
    N1[Call Events (Answer/End)]
    N2[Real-time Notifications]
    N3[Reply to Notifications]
    N4[Media Playback Control]
    N5[Now Playing Info]
  end
  W2 --> N1
  W2 --> N2
  W2 --> N3
  W2 --> N4
  W2 --> N5
