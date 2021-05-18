# Lyrics_Generator
Anyone interested in the project should have fairly good knowledge of deep learning and natural language processing algorithms.
A good knowledge of RNN and LSTM layers is required.

PROCEDURE INVOLVED IN PROJECT MAKING:--->

Created a piano mixed lyrics generation project using LSTM (Long short term memory) and given MIDI files. 
Prepared data from various MIDI file objects and fed it to the LSTM layer model for a sequential generation of lyrics. 
LSTM here avoids vanishing gradient problems and is suitable for such many to one data generation problem. 
MIDI data consisted of 359 different classes of notes and chords of various musical instruments. 
The sequential model is fed with 100 inputs(3D) after being normalized for values between 0 to 358. 
Network outputs are classes that are reverse mapped using the dictionary created at the time of preprocessing. 
Model is monitored using Adam optimizer over "categorical cross-entropy"(trying to minimize it). 
For creating a new sequence of lyrics data is shuffled and picked in linear form having dimensions 100*1*1 with a stride of one from the test set. 
Finally, the predicted text list is generated(around 200 new predictions). 
Text is again converted back to a proper MIDI sound file with variable offsets of the timeline (around 0.5-0.8 units for each predicted object). 
It can be stored on a hard disk. 
The same model if generated again will produce a random state MIDI sound file. 
Variable offset leads to a melodious tone... :)....but it also suffers from the disadvantage that it does not knows that ending or starting should be soft. 
The model is trained for 80-100 epochs but for better accuracy, it could be trained up to 100-200 epochs.
Using Google Colab and its kernel in GPU mode training speed could be enhanced a bit..... :D.
