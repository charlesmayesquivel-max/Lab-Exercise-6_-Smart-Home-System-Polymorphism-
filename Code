public class SmartHomeMain {
    public static void main(String[] args) {

        AirConditioner ac = new AirConditioner();

        LampShade lamp1 = new LampShade(100, "Yellow");
        LampShade lamp2 = new LampShade(lamp1);

        Television tv = new Television();

        Microwave m = new Microwave();

        Device[] devices = { ac, lamp1, lamp2, tv, m };

        System.out.println("\n--- TURNING ON ALL DEVICES ---");
        Device.powerAll(devices, true);

        System.out.println("\nDevices currently ON: " +
                Device.countPoweredOn(devices));

        System.out.println("\n--- TURNING OFF ALL DEVICES ---");
        Device.powerAll(devices, false);

        System.out.println("\nDevices currently ON: " +
                Device.countPoweredOn(devices));
    }
}

/* ---------- PARENT CLASS ---------- */
abstract class Device {
    private boolean isOn;

    public Device() {
        this.isOn = false;
    }

    public void turnOn() {
        isOn = true;
        System.out.println(getClass().getSimpleName() + " is now ON.");
        showStatus();
    }

    public void turnOff() {
        isOn = false;
        System.out.println(getClass().getSimpleName() + " is now OFF.\n");
    }

    public boolean isOn() {
        return isOn;
    }

    public abstract void showStatus();

    public static void powerAll(Device[] devices, boolean powerState) {
        for (Device d : devices) {
            if (powerState) d.turnOn();
            else d.turnOff();
        }
    }

    public static int countPoweredOn(Device[] devices) {
        int count = 0;
        for (Device d : devices) if (d.isOn()) count++;
        return count;
    }
}

/* ---------- CHILD CLASS 1: AIR CONDITIONER ---------- */
class AirConditioner extends Device {
    private int fanSpeed;
    private int temperature;

    public AirConditioner() {
        this.fanSpeed = 3;
        this.temperature = 24;
    }

    public void setFanSpeed(int fanSpeed) {
        this.fanSpeed = fanSpeed;
        showStatus();
    }

    public void setTemperature(int temperature) {
        this.temperature = temperature;
        showStatus();
    }

    @Override
    public void showStatus() {
        if (isOn())
            System.out.println("[AirConditioner Status] Fan Speed: " + fanSpeed +
                    ", Temperature: " + temperature + "°C");
        else
            System.out.println("AirConditioner is off so no settings are displayed.");
    }
}

/* ---------- CHILD CLASS 2: LAMPSHADE ---------- */
class LampShade extends Device {
    private int brightness;
    private String lightColor;

    public LampShade(int brightness, String lightColor) {
        this.brightness = brightness;
        this.lightColor = lightColor;
    }

    public LampShade(LampShade other) {
        this.brightness = other.brightness;
        this.lightColor = other.lightColor;
    }

    public void setBrightness(int brightness) {
        this.brightness = brightness;
        showStatus();
    }

    public void setLightColor(String lightColor) {
        this.lightColor = lightColor;
        showStatus();
    }

    @Override
    public void showStatus() {
        if (isOn())
            System.out.println("[LampShade Status] Brightness: " + brightness +
                    "%, Color: " + lightColor);
        else
            System.out.println("LampShade is off so no settings are displayed.");
    }
}

/* ---------- CHILD CLASS 3: TELEVISION ---------- */
class Television extends Device {
    private int channel;
    private int volume;

    public Television() {
        this.channel = 1;
        this.volume = 10;
    }

    public void setChannel(int channel) {
        this.channel = channel;
        showStatus();
    }

    public void setVolume(int volume) {
        this.volume = volume;
        showStatus();
    }

    @Override
    public void showStatus() {
        if (isOn())
            System.out.println("[Television Status] Channel: " + channel +
                    ", Volume: " + volume + "%");
        else
            System.out.println("Television is off so no settings are displayed.");
    }
}

/* ---------- CHILD CLASS 4: MICROWAVE ---------- */
class Microwave extends Device {
    private int timer;
    private int temperature;

    public Microwave() {
        this.timer = 30;
        this.temperature = 150;
    }

    public void setTimer(int timer) {
        this.timer = timer;
        showStatus();
    }

    public void setTemperature(int temperature) {
        this.temperature = temperature;
        showStatus();
    }

    @Override
    public void showStatus() {
        if (isOn())
            System.out.println("[Microwave Status] Timer: " + timer +
                    "s, Temperature: " + temperature + "°C");
        else
            System.out.println("Microwave is off so no settings are displayed.");
    }
}
