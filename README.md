# AirTagsButWithoutAirTags
Was intrigued by the functionality AirTags provide and hence decided to put my skills to work and build something to find my iPad inside my house. 


Okay, run Location Beacon on the target device with the transmitter Apple AirLocate 5A4BCFCE;
UUID MUST BE '5A4BCFCE-174E-4BAC-A814-092E77F6B7E5'
MAJOR ID- 123
MINOR ID- 456

This setting can be altered if needed inside viewcontroller.swift under the function startScanning.

Now run Project22 (I know the name sucks but you gotta live with it), on your iPhone/iPad/iPod;
It should start working instantly.
Enjoy.

PS; Putting my CLProximity code in here so that you guys know what are the messages you guys are gonna be getting;

 func update(distance: CLProximity) {
        
        UIView.animate(withDuration: 0.1) {
            
            switch distance {
            
            case .unknown:
                self.view.backgroundColor = UIColor.gray
                self.distanceReading.text = "UNKNOWN"
                
            case .far:
                self.view.backgroundColor = UIColor.lightGray
                self.distanceReading.text = "FAR"
                
            case .near:
                
                self.view.backgroundColor = UIColor.darkGray
                self.distanceReading.text = "NEAR"
                
            case .immediate:
                self.view.backgroundColor = UIColor.black
                self.distanceReading.text = "RIGHT HERE"
                

            @unknown default:
                self.view.backgroundColor = .red
                self.distanceReading.text = "WHOA!"
            }
            
            
