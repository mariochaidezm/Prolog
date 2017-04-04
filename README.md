# Prolog
--Implemente una funcion que permita obtener cada parametro
--de una variable tipo Cliente. La funcion recibe una variable tipo
--Cliente y una cadena especificando el parametro que se quiere
-- Obtener. La funcion devuelve.

import Data.Char

--Funciones de alto nivel y aplicaciones de listas
data ClienteR = OrgGubR {nombre :: String}
 | CompaniaR {nombre:: String,numeroID::Int, persona ::PersonaR, posicion :: String}
 | IndividualR {persona :: PersonaR, recibeInformacion :: Bool}
 deriving Show

data PersonaR = PersonaR {nombrePersona :: String, apellido :: String , genero :: Genero}
 deriving Show

data Genero = Hombre | Mujer | Desconocido
 deriving Show


----Funcion que establece el nombre  de una persona con iniciales en mayusculas
nombreMayuscula :: PersonaR -> PersonaR
nombreMayuscula p @ (PersonaR {nombrePersona = x:xs}) = 
 let nuevoNombre =  (toUpper x):xs
 in p {nombrePersona = nuevoNombre}
