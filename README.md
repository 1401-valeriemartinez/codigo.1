from abc import ABC, abstractmethod # Modulo que permite crear clases abstractas

# Definición de la clase abstracta
class Forma_de_pago(ABC):
    def _init_(self, Cliente, Monto, Fecha):
      self.Cliente = Cliente
      self.Monto = Monto
      self.Fecha = Fecha
        

# Método obligatorio a ser implementado en las subclases
    @abstractmethod
    def realizar_pago(self):
        pass

# Subclase para formas de pago
class Efectivo(Forma_de_pago):
    def realizar_pago(self, ):
        return f"El cliente:{self.Cliente}, Pagó:{self.Monto}, El dia:{self.Fecha}"

class NEQUI(Forma_de_pago):
    def _init_(self, Cliente, Monto, Fecha, Por):
        super()._init_(Cliente, Monto, Fecha)
        self.Por = Por
         #Super es una función que permite llamar método de una clase padre
        
    def realizar_pago(self):
         return f"El cliente:{self.Cliente}. Pagó:{self.Monto}, El dia:{self.Fecha}, Por:{self.Por}"

class Daviplata(Forma_de_pago):
    def _init_(self, Cliente, Número_cuenta, Monto, Fecha, Por):
        super()._init_(Cliente, Monto, Fecha)
        self.Número_cuenta = Número_cuenta
        self.Por = Por

    def realizar_pago(self):
         return f"El cliente:{self.Cliente}. Pagó:{self.Monto}, Con el número de cuenta:{self.Número_cuenta}, El dia:{self.Fecha}, Por:{self.Por}"

class Tarjeta_de_credito(Forma_de_pago):
    def _init_(self, Cliente, Número_cuenta, Monto, Fecha, Por):
        super()._init_(Cliente, Monto, Fecha)
        self.Número_cuenta = Número_cuenta
        self.Por = Por               

    def realizar_pago(self):
         return f"El cliente:{self.Cliente}. Pagó:{self.Monto}, Con el número de cuenta:{self.Número_cuenta}, El dia:{self.Fecha}, Por:{self.Por}"
 
class Tarjeta_de_debito(Forma_de_pago):
    def _init_(self, Cliente, Número_cuenta, Monto, Fecha, Por):
        super()._init_(Cliente, Monto, Fecha)
        self.Número_cuenta = Número_cuenta
        self.Por = Por

    def realizar_pago(self):
         return f"El cliente:{self.Cliente}. Pagó:{self.Monto}, Con el número de cuenta:{self.Número_cuenta}, El dia:{self.Fecha}, Por:{self.Por}"
    
class PSE(Forma_de_pago):
    def _init_(self, Cliente, Monto, Fecha, Por):
        super()._init_(Cliente, Monto, Fecha)
        self.Por = Por
         #Super es una función que permite llamar método de una clase padre
        
    def realizar_pago(self):
         return f"El cliente:{self.Cliente}. Pagó:{self.Monto}, El dia:{self.Fecha}, Por:{self.Por}"

#Crear instancias de las suIbclases
efectivo = Efectivo("natalia tovar", "62.300", "22/03/25")
nequi = NEQUI("nicol gomez", "50.000", "20/03/25", "Nequi")
daviplata = Daviplata("isabel suarez", "3181123755", "10.000", "16/12/25", "Daviplata")
tarjeta_de_credito = Tarjeta_de_credito("valerie amaya", "5105 1051 0510 5100", "500.000", "06/02/25", "Tarjeta de credito")
tarjeta_de_debito =Tarjeta_de_debito("santiago peña", "4242 4242", "1.500.000", "02/07/25", "Tarjeta de debito")
pse = PSE("ximena betancourt", "250.000", "04/12/25", "PSE")

# Mostrar la información de cada estudiante
print(efectivo.realizar_pago())
print(nequi.realizar_pago())
print(daviplata.realizar_pago())
print(tarjeta_de_credito.realizar_pago())
print(tarjeta_de_debito.realizar_pago())
print(pse.realizar_pago())# codigo.1
