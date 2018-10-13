# 2018.10.11 DL-gyak



##  *Tensorflow*

* Számítási gráfokban gondolkodik

* Mindig hivatkozni kell a gráfra amit módosítani akarok 

* placeholder --> ide várja  a bemenetet --> olyan mint egy variable, lefoglal memória területet, de még semmi konkrét (lehetne látni a memória szemetet)

* súlymátrixot is definiálni kell  --> a mátrix egy variable lesz

* bias-okat is kell definiálni --> ez pedig egy vektor variable lesz 

* sess.run - nal tudunk végrehajtani valamit a gráfon

* sess.run(tf.global_variables_initalizier) --> lefoglalja a variable-nek, placeholderek-nek a helyeket

* Van a tesorflow-nak olyan nyelvjárása, ahol könnyebben lehet építeni hálót --> lehet érdemesebb akkor már a keras

* X bemeneti vektor --> szorozzuk W súllyal --> hozzá adjuka biast --> hatatjuk rá az aktivácós függvényt --> ez eredményezi az y vektort, ami most a kimenet

* ```python
  y = tf.nn.softmax(tf.matmul(x, W) + b) 
  ```

  Saját hiba függvényt kell definiálni --> y_ a predikciója a hálózatnak --> tesnor flow saját matek függvényt használjuk, mert a tensorflow tensor objektimai nem sima numpy tömbök

  ```python
  cross_entropy = tf.reduce_mean(-tf.reduce_sum(y_ * tf.log(y- ), reduction_indices=[1])
  ```

* Defeniáltunk egy tanítási lépést --> GSD --> a cél a cross_entropy minimalizálása --> ezt kéne többször futtatni

* ```python
  train_step = tf.train.GradientDescentOptimizer(0.5).minimize(cross_entropy)
  ```

* Itt most nem epoch-szerűen dolgozunk, hanem csak definiálunk 1000 lépést

  * ebben a megvalósításban figyelnünk kell, hogy a batch_counter ne menjen túl a rendelkezésre álló adatokon, így azt nullázni kell néha

* ```python
  batch_counter = 0
  for i in range(1000):
    train_step.run(session=sess, feed_dict={x: x_train[batch_counter*batch_size:														 (batch_counter+1)*batch_size]
                                            , y_: y_train[batch_counter*batch_size:													(batch_counter+1)*batch_size]})
    batch_counter += 1
    if (batch_counter*batch_size) > len(x_train):
      batch_counter = 0
  ```

* Difináljuk az elején egy session-t --> azután minden megy egybe --> jó jelölés lehetne, hogy:

  * a tf.nn.softmax hozza létre valójában a szükséges réteget nekünk a session-belül

* ```python
  with sess in tf.seesion():
  	valami ami az adott gráfba megy
  ```

* Az hogy valamit leírok nem biztos h le is fut --> akkor fut csak le ha kell valami másnak vagy ha pl.: printtelni kell

* 