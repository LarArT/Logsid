### Représentation des premiers entiers naturels avec différents codes

| Base 1 | Unaire | Binaire (sur 8 bits) | Décimal | Nombre de Church |
| :---: | :---: | :---: | :---: | :--- |
| | 0 | 0000 0000 | 0 | $\lambda f \cdot \lambda x \cdot x$ |
| 1 | 10 | 0000 0001 | 1 | $\lambda f \cdot \lambda x \cdot fx$ |
| 11 | 110 | 0000 0010 | 2 | $\lambda f \cdot \lambda x \cdot f(fx)$ |
| 111 | 1110 | 0000 0011 | 3 | $\lambda f \cdot \lambda x \cdot f(f(fx))$ |
| 1111 | 1 1110 | 0000 0100 | 4 | $\lambda f \cdot \lambda x \cdot f(f(f(fx)))$ |
| 1 1111 | 11 1110 | 0000 0101 | 5 | $\lambda f \cdot \lambda x \cdot f(f(f(f(fx))))$ |