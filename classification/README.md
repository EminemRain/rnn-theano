#Classification Model - RNN based on theano
#ʹ��Theanoʵ�ֵ�RNN��ط���ģ��

ģ��MLSTM���ģ�[����](http://arxiv.org/pdf/1512.08849.pdf)

##��������

	ʹ��ʱ����setting.py���޸��������������ӳ��ȣ�batch��С���ʵ��С�Ȼ�������
	
	g_max_length = 100	# ���ɾ��ӵ���󳤶�
	g_n_epoch = 100	# ��������
	g_save_epoch = 2	# ģ�ͱ�����
	g_learning_rate = 0.001	# ѧϰ�� RmsProp
	g_decay = 0.95	# RmsProp�е�decay
	g_batch_size = 64	# batch�Ĵ�С
	g_sen_len = 15	# ���ӵĳ���
	g_hidden_dim = 256	# ���������
	g_word_dim = 16531 + 2 # �ֵ��С + 2
	G_MODEL = LSTM	# ģ�ͣ�Ŀǰ���õ���RNN��LSTM�Լ�MLSTM
	
	
##ʹ�÷���

**For training,**
	
	python train.py -t data_train_file data_test_file data_dic_file data_class_weights model_save_file pre_trained_file(optional)
		data_train_file, train data
		data_test_file, test data
		data_class_weights, class weights, format: "label,weights,count,class_name"
    
**For prediction,**
    
	python train.py -p model_file dic_file predict_data_file result_save_file