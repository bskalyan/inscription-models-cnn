# inscription-models-cnn
inscription models cnn
python -m scripts.retrain --bottleneck_dir=tf_files/bottlenecks --how_many_training_steps=30 
--model_dir=tf_files/models/ --summaries_dir=tf_files/training_summaries/mobilenet_1.0_224
--output_graph=tf_files/retrained_graph.pb --output_labels=tf_files/retrained_labels.txt  --learning_rate=0.0001
--optimiser=GradientDescent --architecture=mobilenet_1.0_224 --image_dir=C:/User --activation_fnc=softmax 

============
python -m scripts.label_image --graph=tf_files/retrained_graph.pb --image=tf_files/test_set/ig(1).jpg

python -m scripts.label_image --graph=tf_files/retrained_graph.pb --image=tf_files/test_set/ig(1).jpg 

tensorboard --logdir=tf_files/training_summaries/mobilenet_1.0_224   --port=8080

===========
tensorboard --logdir=tf_files/training_summaries/mobilenet_1.0_224   --port=8080

==========
python -m scripts.retrain --bottleneck_dir=tf_files/bottlenecks --how_many_training_steps=3500 
--model_dir=tf_files/models/ --summaries_dir=tf_files/training_summaries/inception_v3
--output_graph=tf_files/retrained_graph.pb --output_labels=tf_files/retrained_labels.txt 
----train_batch_size=50 validation_batch_size=-2 --learning_rate=0.001 --optimiser=Ftrl 
--architecture=inception_v3 --image_dir=tf_files/train_landmarks --activation_fnc=softmax --keep_prob=0.40

