
//define analog input to our Moisture, Light and Temperature Sensors
int moistureSensor = 0;
int lightSensor = 1;
int tempSensor = 2;

//define variables to store Moisture, Light and Temperature values
int moisture_val;
int light_val;
int temp_val;

void setup() {
  //open serial port
  Serial.begin(9600);
  
  /*Define PinModes for LED Outputs (odd pins- RED and even pins-YELLOW) */
  pinMode(13,OUTPUT);
  pinMode(12,OUTPUT);
  pinMode(11,OUTPUT);
  pinMode(10,OUTPUT);
  pinMode(9,OUTPUT);
  pinMode(8,OUTPUT);
}

void loop() {
  
  
  /**************MOISTURE SENSOR***************/
  
  moisture_val = analogRead(moistureSensor);
  Serial.print("The value read by Moisture Sensor is ");
  Serial.println(moisture_val);
  
  //turn RED LED on when soil is dry, and turn on YELLOW LED if soil is wet

  if (moisture_val < 300)
  {
    Serial.println("Feed me! Feed me! I'm Thirsty\n\n");
    digitalWrite(13,HIGH);//blink RED LED
    delay(2000);
    digitalWrite(13,LOW);
    delay(2000);
  }
  else
  {
    Serial.println(" Yo! I'm healthy!\n\n ");
    digitalWrite(12,HIGH);//blink YELLLOW LED
    delay(2000);
    digitalWrite(12,LOW);
    delay(2000);
    
  }
  
  
  /************LIGHT SENSOR****************/
    
  light_val = analogRead(lightSensor);
  Serial.print("The value read by Light Sensor is ");
  Serial.println(light_val);
  
  
  
  //turn RED LED on if light is low is dry, and turn on YELLOW LED if light is optimum
  if (light_val < 300)
  {
    Serial.println("Ufff! I need some light buddies!\n\n");
    digitalWrite(11,HIGH);//blink RED LED
    delay(2000);
    digitalWrite(11,LOW);
    delay(2000);
  }
  else
  {
    Serial.println(" I'm bright and Sunny!\n\n ");
    digitalWrite(10,HIGH);//blink YELLLOW LED
    delay(2000);
    digitalWrite(10,LOW);
    delay(2000);
    
  }
  
  
  /************TEMPERATURE SENSOR****************/
    
  temp_val = analogRead(tempSensor);
  Serial.print("The value read by Temperature Sensor is ");
  Serial.println(temp_val);
  
  
  //turn RED LED on when temperature is low, and turn on YELLOW LED if temperature is optimum
  
  if (temp_val < 300)
  {
    Serial.println("I'm feeling cold.. Give me some sunshine\n\n");
    digitalWrite(9,HIGH);//blink RED LED
    delay(2000);
    digitalWrite(9,LOW);
    delay(2000);
  }
  else
  {
    Serial.println(" Yo! I'm basking in the sun\n\n ");
    digitalWrite(8,HIGH);//blink YELLLOW LED
    delay(2000);
    digitalWrite(8,LOW);
    delay(2000);
    
  }
  
}
