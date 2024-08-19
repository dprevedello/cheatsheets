

# Operazioni di Algebra Lineare per la Computer Grafica

## Introduzione

L'algebra lineare è fondamentale nella computer grafica, poiché molte delle operazioni comuni come la trasformazione, la rotazione e la proiezione si basano su concetti di algebra lineare come vettori, matrici e spazi vettoriali.

## Vettori

### Descrizione

Un vettore è un'entità matematica che ha una magnitudine e una direzione. In computer grafica, i vettori sono utilizzati per rappresentare punti, direzioni e velocità. I vettori in uno spazio 2D o 3D sono comunemente rappresentati come tuple di numeri reali.

### Esempio

Un vettore in uno spazio 3D può essere rappresentato come:

$$
\mathbf{v} = \begin{pmatrix} x \\ y \\ z \end{pmatrix}
$$

### Operazioni con i Vettori

#### Addizione di Vettori

L'addizione di due vettori è effettuata sommando i componenti corrispondenti:

$$
\mathbf{v_1} + \mathbf{v_2} = \begin{pmatrix} x_1 \\ y_1 \\ z_1 \end{pmatrix} + \begin{pmatrix} x_2 \\ y_2 \\ z_2 \end{pmatrix} = \begin{pmatrix} x_1 + x_2 \\ y_1 + y_2 \\ z_1 + z_2 \end{pmatrix}
$$

#### Moltiplicazione per uno Scalare

La moltiplicazione di un vettore per uno scalare è definita come:

$$
a \cdot \mathbf{v} = a \cdot \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} a \cdot x \\ a \cdot y \\ a \cdot z \end{pmatrix}
$$

### Esempio in Python

```python
import numpy as np

# Definizione di due vettori
v1 = np.array([1, 2, 3])
v2 = np.array([4, 5, 6])

# Addizione di vettori
v_sum = v1 + v2

# Moltiplicazione per uno scalare
scalar = 3
v_scaled = scalar * v1

print("Addizione dei vettori:", v_sum)
print("Moltiplicazione per uno scalare:", v_scaled)
```

## Matrici

### Descrizione

Una matrice è una tabella bidimensionale di numeri che rappresenta una trasformazione lineare. In computer grafica, le matrici sono utilizzate per trasformare vettori in modo efficiente, come nel caso della rotazione, della traslazione e della scala.

### Esempio

Una matrice 3x3 per la rotazione in uno spazio 3D è rappresentata come:

$$
\mathbf{R} = \begin{pmatrix} r_{11} & r_{12} & r_{13} \\ r_{21} & r_{22} & r_{23} \\ r_{31} & r_{32} & r_{33} \end{pmatrix}
$$

### Operazioni con le Matrici

#### Moltiplicazione Matrice-Vettore

La moltiplicazione di una matrice per un vettore è definita come:

$$
\mathbf{R} \cdot \mathbf{v} = \begin{pmatrix} r_{11} & r_{12} & r_{13} \\ r_{21} & r_{22} & r_{23} \\ r_{31} & r_{32} & r_{33} \end{pmatrix} \cdot \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} r_{11}x + r_{12}y + r_{13}z \\ r_{21}x + r_{22}y + r_{23}z \\ r_{31}x + r_{32}y + r_{33}z \end{pmatrix}
$$

#### Moltiplicazione Matrice-Matrice

La moltiplicazione di due matrici è effettuata moltiplicando le righe della prima matrice per le colonne della seconda:

$$
\mathbf{A} \cdot \mathbf{B} = \mathbf{C}
$$

dove:

$$
C_{ij} = \sum_{k} A_{ik} \cdot B_{kj}
$$

### Esempio in Python

```python
import numpy as np

# Definizione di una matrice e di un vettore
R = np.array([[1, 0, 0],
              [0, 1, 0],
              [0, 0, 1]])

v = np.array([1, 2, 3])

# Moltiplicazione matrice-vettore
v_transformed = np.dot(R, v)

print("Vettore trasformato:", v_transformed)
```

## Trasformazioni 3D

### Descrizione

Le trasformazioni in 3D, come la rotazione, la traslazione e la scala, sono essenziali per manipolare oggetti in uno spazio tridimensionale.

### Rotazione

La matrice di rotazione attorno all'asse z è data da:

$$
\mathbf{R_z}(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta & 0 \\ \sin\theta & \cos\theta & 0 \\ 0 & 0 & 1 \end{pmatrix}
$$

### Traslazione

La traslazione di un vettore è ottenuta aggiungendo un vettore di traslazione:

$$
\mathbf{v'} = \mathbf{v} + \mathbf{t}
$$

dove:

$$
\mathbf{t} = \begin{pmatrix} t_x \\ t_y \\ t_z \end{pmatrix}
$$

### Scala

La trasformazione di scala è rappresentata da una matrice diagonale:

$$
\mathbf{S} = \begin{pmatrix} s_x & 0 & 0 \\ 0 & s_y & 0 \\ 0 & 0 & s_z \end{pmatrix}
$$

### Esempio in Python

```python
import numpy as np

# Definizione di un angolo di rotazione
theta = np.pi / 4

# Matrice di rotazione attorno all'asse z
R_z = np.array([[np.cos(theta), -np.sin(theta), 0],
                [np.sin(theta),  np.cos(theta), 0],
                [0, 0, 1]])

# Vettore da trasformare
v = np.array([1, 0, 0])

# Applicazione della rotazione
v_rotated = np.dot(R_z, v)

print("Vettore ruotato:", v_rotated)
```

---

# Operazioni Avanzate di Algebra Lineare

## 1. Prodotto Scalare (Dot Product)

### Descrizione

Il prodotto scalare è un'operazione tra due vettori che restituisce un singolo numero (scalare). È usato per calcolare l'angolo tra due vettori e per determinare l'ortogonalità.

### Formula

Dato due vettori \(\mathbf{v_1}\) e \(\mathbf{v_2}\):

$$
\mathbf{v_1} \cdot \mathbf{v_2} = x_1 \cdot x_2 + y_1 \cdot y_2 + z_1 \cdot z_2
$$

### Esempio in Python

```python
import numpy as np

v1 = np.array([1, 2, 3])
v2 = np.array([4, 5, 6])

# Calcolo del prodotto scalare
dot_product = np.dot(v1, v2)

print("Prodotto scalare:", dot_product)
```

### Applicazione

Il prodotto scalare è utilizzato per calcolare la luminosità in un modello di illuminazione Phong, dove la luce incidente su una superficie è calcolata in base all'angolo tra la direzione della luce e la normale alla superficie.

## 2. Prodotto Vettoriale (Cross Product)

### Descrizione

Il prodotto vettoriale è un'operazione tra due vettori in uno spazio tridimensionale che restituisce un nuovo vettore perpendicolare al piano definito dai due vettori originali. È utilizzato per calcolare normali alle superfici e per determinare l'orientazione di oggetti.

### Formula

Dato due vettori \(\mathbf{v_1}\) e \(\mathbf{v_2}\):

$$
\mathbf{v_1} \times \mathbf{v_2} = \begin{pmatrix} y_1 \cdot z_2 - z_1 \cdot y_2 \\ z_1 \cdot x_2 - x_1 \cdot z_2 \\ x_1 \cdot y_2 - y_1 \cdot x_2 \end{pmatrix}
$$

### Esempio in Python

```python
v1 = np.array([1, 0, 0])
v2 = np.array([0, 1, 0])

# Calcolo del prodotto vettoriale
cross_product = np.cross(v1, v2)

print("Prodotto vettoriale:", cross_product)
```

### Applicazione

Il prodotto vettoriale è comunemente utilizzato per calcolare la normale di una superficie, necessaria per operazioni di shading (ombreggiatura) e rendering.

## 3. Determinante di una Matrice

### Descrizione

Il determinante è un valore scalare associato a una matrice quadrata che fornisce informazioni su alcune proprietà della matrice, come l'invertibilità e il volume scalato della trasformazione lineare rappresentata dalla matrice.

### Formula

Per una matrice \(2 \times 2\):

$$
\text{det}(\mathbf{A}) = \begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc
$$

Per una matrice \(3 \times 3\):

$$
\text{det}(\mathbf{A}) = a(ei - fh) - b(di - fg) + c(dh - eg)
$$

### Esempio in Python

```python
A = np.array([[1, 2], [3, 4]])

# Calcolo del determinante
det_A = np.linalg.det(A)

print("Determinante:", det_A)
```

### Applicazione

Il determinante è usato per verificare se una matrice è invertibile (una matrice è invertibile se il suo determinante è diverso da zero) e per calcolare l'area o il volume di oggetti trasformati.

## 4. Inversa di una Matrice

### Descrizione

L'inversa di una matrice è una matrice che, moltiplicata per la matrice originale, restituisce la matrice identità. In computer grafica, l'inversa è utilizzata per invertire trasformazioni, come tornare alla posizione originale di un oggetto dopo aver applicato una serie di trasformazioni.

### Formula

Per una matrice \(2 \times 2\):

$$
\mathbf{A}^{-1} = \frac{1}{\text{det}(\mathbf{A})} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
$$

### Esempio in Python

```python
A = np.array([[1, 2], [3, 4]])

# Calcolo dell'inversa
A_inv = np.linalg.inv(A)

print("Matrice inversa:\n", A_inv)
```

### Applicazione

L'inversa è essenziale quando si devono annullare trasformazioni o quando si vuole trasformare un oggetto da un sistema di coordinate a un altro.

## 5. Autovalori e Autovettori

### Descrizione

Gli autovalori e gli autovettori sono utilizzati per analizzare le proprietà di una matrice. Un autovettore di una matrice è un vettore che, quando moltiplicato per la matrice, restituisce un vettore che è una scala del vettore originale. L'autovalore è questo fattore di scala.

### Formula

Data una matrice \(\mathbf{A}\) e un vettore \(\mathbf{v}\), \(\lambda\) è un autovalore se:

$$
\mathbf{A} \mathbf{v} = \lambda \mathbf{v}
$$

### Esempio in Python

```python
A = np.array([[1, 2], [2, 1]])

# Calcolo di autovalori e autovettori
eigenvalues, eigenvectors = np.linalg.eig(A)

print("Autovalori:", eigenvalues)
print("Autovettori:\n", eigenvectors)
```

### Applicazione

In computer grafica, gli autovalori e gli autovettori possono essere utilizzati per la decomposizione delle matrici, analizzando la deformazione degli oggetti e nella riduzione della dimensionalità per l'elaborazione delle immagini.

## 6. Trasposta di una Matrice

### Descrizione

La trasposta di una matrice è ottenuta scambiando le righe con le colonne. È spesso utilizzata in combinazione con altre operazioni per manipolare matrici in modo più efficiente.

### Formula

La trasposta di una matrice \(\mathbf{A}\) è denotata come \(\mathbf{A}^T\):

$$
\mathbf{A}^T_{ij} = \mathbf{A}_{ji}
$$

### Esempio in Python

```python
A = np.array([[1, 2], [3, 4]])

# Calcolo della trasposta
A_T = np.transpose(A)

print("Matrice trasposta:\n", A_T)
```

### Applicazione

La trasposta è utilizzata nel calcolo del prodotto scalare, nell'algoritmo di shading Phong, e in molte altre operazioni di algebra lineare.

## 7. Decomposizione in Valori Singolari (SVD)

### Descrizione

La decomposizione in valori singolari è una tecnica per scomporre una matrice in tre matrici: una matrice di rotazione, una matrice di scala, e una matrice di rotazione trasposta. È ampiamente usata nel trattamento delle immagini, compressione dei dati e altre applicazioni di grafica.

### Formula

Per una matrice \(\mathbf{A}\), la decomposizione SVD è:

$$
\mathbf{A} = \mathbf{U} \mathbf{\Sigma} \mathbf{V}^T
$$

Dove \(\mathbf{U}\) e \(\mathbf{V}\) sono matrici ortogonali e \(\mathbf{\Sigma}\) è una matrice diagonale con i valori singolari.

### Esempio in Python

```python
A = np.array([[1, 2], [3, 4]])

# Decomposizione SVD
U, S, Vt = np.linalg.svd(A)

print("Matrice U:\n", U)
print("Matrice S (valori singolari):\n", S)
print("Matrice V trasposta:\n", Vt)
```

### Applicazione

L'SVD è usata in applicazioni come la compressione delle immagini, la riduzione della dimensionalità, e la risoluzione di sistemi lineari mal condizionati.
