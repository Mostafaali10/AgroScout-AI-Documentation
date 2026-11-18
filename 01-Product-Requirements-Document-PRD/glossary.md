# AgroScout AI — System Glossary & Terminology

> **Status**: Draft – Derived from Source File  
> **Module**: PRD Foundations  
> **Source Reference**: `Source File.docx` (§1, §2, §3, §4, §5)

---

## 1. Domain & Agricultural Terms

- **AgroScout AI**: A smart agriculture monitoring and AI-assisted crop inspection platform combining mobile, backend, AI vision, drone/camera imagery, and IoT ground nodes `(Source: §1)`.
- **Early Disease Detection**: The identification of visual disease patterns and infection symptoms on crops at initial stages to restrict disease spread, replace blanket chemical spraying with targeted treatment, and protect crop yield, quality, and farm revenue `(Source: §1)`.
- **FAO Benchmark**: The statistical reference from the Food and Agriculture Organization (FAO, 2021) cited in project notes, indicating that 20% to 40% of global crop production is lost annually to pests and diseases `(Source: §1)`.
- **Field Scouting**: The process of surveying crop fields to inspect crop health, identify disease symptoms, and assess weed/pest conditions `(Source: §1, §3 F8)`.
- **Foliar Pathogen / Plant Disease**: Biological infections on crop leaves manifesting visual discoloration, lesions, spots, or blight that can be analyzed via computer vision `(Source: §1, §3 F11, §3 F12)`.

---

## 2. IoT & Hardware Terms

- **Ground Node**: An on-field micro-station built around the ESP32 microcontroller that acquires environmental and soil readings and communicates telemetry to the backend `(Source: §1, §5)`.
- **ESP32**: The core proposed microcontroller responsible for reading sensor inputs and communicating ground-node telemetry `(Source: §5)`.
- **DHT22**: The core proposed digital sensor for measuring ambient air temperature and relative humidity `(Source: §5)`.
- **Capacitive Soil Moisture Sensor**: The core proposed soil probe that measures soil moisture levels via capacitive sensing `(Source: §5)`.
- **Battery Voltage Monitor**: An optional hardware module that measures and reports ground-node battery voltage levels to warn of low battery states `(Source: §5)`.
- **Leaf Wetness Sensor**: An optional sensor measuring moisture levels present on crop leaf surfaces `(Source: §5)`.
- **DS18B20**: An optional waterproof temperature probe for localized soil or liquid temperature measurement `(Source: §5)`.

---

## 3. Imaging & Capture Devices

- **ESP32-CAM**: A low-cost camera option under consideration for testing the basic image pipeline (camera → image/stream transfer → app/system → AI → bounding box); limited in image quality and dynamic range `(Source: §5)`.
- **Mobile Phone Camera**: The built-in smartphone camera utilizing the device's native GPS for direct crop image capture and early workflow validation `(Source: §5)`.
- **Raspberry Pi Zero 2 W + Camera Module 3**: A higher-fidelity camera option under consideration for simulating dedicated drone-mounted capture, offering autofocus, superior quality, and lower latency `(Source: §5)`.

---

## 4. Software & Architecture Terms

- **Clean Architecture**: The software architecture pattern designated for the Flutter mobile application, separating domain, data, and presentation layers for maintainability and testability `(Source: §5)`.
- **BLoC / Cubit**: The state management framework designated for the Flutter mobile application `(Source: §5)`.
- **Backend-Based Processing**: The architectural strategy whereby plant disease inference and image analysis are executed centrally on the Backend, rather than locally on the edge device `(Source: §2, §5)`.
- **Offline Mode & Synchronization**: The mobile application capability to persist captured images, sensor readings, and inspection metadata locally without internet access, queuing them for upload upon connectivity restoration `(Source: §3 F6)`.
- **Synchronization Lifecycle States**: The formal operational statuses assigned to offline records: `Pending Upload`, `Uploading`, `Processing`, `Completed`, and `Failed` `(Source: §3 F6)`.
- **Scouting Mission Lifecycle States**: The operational statuses tracking field inspection tasks: `Pending`, `In Progress`, and `Completed` `(Source: §3 F8)`.
- **AI Agricultural Agent**: An interactive conversational assistant providing agronomic insights, symptom explanations, causes, prevention advice, and suggested treatments with explicit communication of diagnosis uncertainty `(Source: §3 F12)`.
