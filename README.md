# TF-and-JSON
JSON communication message with Tensorflow

🧸💬 Development environment preparation, Python virtual environment with bash command integration. In development environments, you may have requirements to develop the same library with multiple versions in the version control step of CI/CD software development or need to perform development with different Kernel and cloud accounts to help with virtual environment setup. </br>
🐑💬 ➰ For network communications binary message is ready for pop message integration or you can perform the same task using local library formats. </br>

<p align="center" width="100%">
    <img width="50%" src="https://github.com/jkaewprateep/TF-and-JSON/blob/main/tensorflow_01.png">
    <img width="22.26%" src="https://github.com/jkaewprateep/TF-and-JSON/blob/main/kid_32.jpg">
    <img width="22.26%" src="https://github.com/jkaewprateep/TF-and-JSON/blob/main/kid_36.jpg"> </br>
    <b> Learning TensorFlow SDK and Python codes </b> </br>
</p>
</br>
</br>

🐐💬 Anaconda console for virtual environment management, integration with online templates, and local virtual environment or performed by activated virtual in Python or parallel desktop in multiple development platforms. </br>
🦭💬 In some machine learning remote distribution will only receive communication in binary format or require installed Tensorflow at the destination, there are Tensorflow lite, networks conversion, or direct communication using IC circuits. </br>
🐯💬 Culture INFO, by communication needs to be performed on both terminals with the same information requirements as agreed, process, or compressed may add overhead to the message in the manner of terminals having the same message information with their performance-activated method. </br>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/jkaewprateep/TF-and-JSON/blob/main/virtual_environment_01.png"> </br>
    <b> Anaconda virtual environment </b> </br>
</p>
</br>
</br>

🦁💬 A virtual environment is identified by its access level to data sources and executable on an object. The level access authority can activate and execute on the target destination, or they can perform restore and tracking. Still, the results from execution on the primary are not a virtual environment. </br>
🦭💬 They are utility help for managing data information and backup restore with the ability to perform tasks like installing of multiple configuration sets on the same OS and data resources. </br>
🐯💬 Culture INFO, performed on the same machine or remote application will identify and locate of sensitivity of data and actions for the results performed. </br>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/jkaewprateep/TF-and-JSON/blob/main/directory_access.png"> </br>
    <b> Directory access </b> </br>
</p>
</br>
</br>

🧸💬 Binary conversion format will support many remote device machines because they can directly apply without processing or less processing format ( 👨🏻‍🏫💬 Less processing format that is the rule ) and you can perform encryption overhead. </br>
🐐💬 You may refer to an example for remote device communication such as a television remote controller or player [example]( https://github.com/jkaewprateep/Remote_devices/blob/main/README.md ) </br>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/jkaewprateep/TF-and-JSON/blob/main/TF_traindataset_valueconversion.png"> </br>
    <b> Tensorflow training dataset creation, binary conversion, JSON phasing, and data extraction </b> </br>
</p>
</br>
</br>

🐑💬 ➰ Even image transfer in data communication, string or array integer values for training dataset application in Financial banking, Insurance, IT & Telecommunication, and Government business. </br>
🦁💬 Image information can be transferred with signature or binary number format for data verification because they are logging, reverse transformable, and replace or modify use more effort for speed communication is a hardship skill. </br>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/jkaewprateep/TF-and-JSON/blob/main/image_dataset.png"> </br>
    <b> Data extraction features dataset </b> </br>
</p>
</br>
</br>

[Create image dataset]( https://github.com/jkaewprateep/json_data_set/blob/main/README.md )</br>
[Simple Tensorflow for sequential data learning and prediction]( https://github.com/jkaewprateep/Simple_Tensorflow_sequentialdata/blob/main/README.md )</br>
[Consume HTTP rest services with a simple method with Alpaca RESTFul services API]( https://github.com/jkaewprateep/Python-HTTP-simple/blob/main/README.md )</br>

## Example codes ##

```
import requests;
import json;
import tensorflow as tf;
#
from google.protobuf import json_format;
import logging, os
logging.disable(logging.WARNING)
os.environ["TF_CPP_MIN_LOG_LEVEL"] = "3"


url = "https://paper-api.alpaca.markets/v2/account";

headers = { 'content-type': 'application/json', "APCA-API-KEY-ID": "**********", "APCA-API-SECRET-KEY": "*************", 
    "Accept": "*/*", "User-Agent": "🐑💬 ➰ DekDee" };

response = requests.get( url, headers=headers, verify = False );
data = json.loads(response.content)
# print(data);

data_features_1 = [ data["options_trading_level"], data["buying_power"], data["cash"], data["sma"] ];
data_features_1 = [ int(x) for x in data_features_1 ];
print( "Create data features." );
print( data_features_1 );
print( os.linesep );
data_features_2 = [ data["options_trading_level"], data["buying_power"], data["cash"], data["sma"] ];
data_features_2 = [ int(x) for x in data_features_2 ];
# print( data_features_2 );

#
example = tf.train.Example(
	features=tf.train.Features(
		feature={
			"1": tf.train.Feature(
			
				int64_list=tf.train.Int64List(
					value=tf.constant( data_features_1, shape=( 4 * 1 * 1 ) ).numpy() )
					
					),
			"2": tf.train.Feature(
			
				int64_list=tf.train.Int64List(
					value=tf.constant( data_features_2, shape=( 4 * 1 * 1 ) ).numpy() )
					
					)		
			}));
#


data_string = json_format.MessageToJson(example)
example_binary = tf.io.decode_json_example(data_string)


example_phase = tf.io.parse_example(
	serialized=[example_binary.numpy()],
	features = { 	"1": tf.io.FixedLenFeature(shape=[ 4 * 1 * 1 ], dtype=tf.int64),
			"2": tf.io.FixedLenFeature(shape=[ 4 * 1 * 1 ], dtype=tf.int64)
				});
                
print( "Create binary data features." );
print( example_binary );
print( os.linesep );

data = list(example_phase.items())
label = [ int(x[0]) for x in data ]

print( "Sample of data extraction." );
print( data );
print( os.linesep );
print( "Sample of label extraction." );
print( label );
print( os.linesep );
print( "Sample of Numpy array converstaion." );
print( data[0][1]._numpy() );

print( os.linesep );
```

---

<p align="center" width="100%">
    <img width="30%" src="https://github.com/jkaewprateep/advanced_mysql_topics_notes/blob/main/custom_dataset.png">
    <img width="30%" src="https://github.com/jkaewprateep/advanced_mysql_topics_notes/blob/main/custom_dataset_2.png"> </br>
    <b> 🥺💬 รับจ้างเขียน functions </b> </br>
</p>
