# AppTela
INDEX

import React from "react";

import {Text, View, Image, TextInput, TouchaOpacity, Alert} from 'react-native';



import { style } from "./styles";
import Logo from '../../assets/logo.png'
import {MaterialIcons} from '@expo/vector-icons';
import { themas } from "../../global/themes"
export default function Login (){
	const [email,setEmail] = useState('');
	const [password,setPassword] = useState('');


	function getLogin(){
		try {

		     if(!email  ||  !password){
			return Alert.alert('Atenção','Informe os campos obrigatórios!')
		}

		console.log('Logado com sucesso')

	}catch (error) {
	     console.log(error)
	     }

	}

	return(
		<View styles={style.container}>
		  <View style={style.boxTop}>
			<Image
			     source={Logo}
			     style={style.logo}
			     resizeMode="contain"
			/>
			<Text style={style.text}>Bem-vindo de volta! </Text>
		  </View>
		  <View style={style.boxMid}>
			<Text style={style.titleInput}>ENDEREÇO DE E-MAIL</Text>
			<View style={style.BoxInput}> 
				<TextInput
					style={style.input}
					value={email}
					onChangeText={setEmail}
				 />
				<MaterialIcons 
					name= 'email'
					size={20}
					themas{themas.color.gray}
				 />
			</View>
			<View style={style.BoxInput}> 
				<TextInput
					style={style.input}
				 />
				<MaterialIcons 
					name= 'remove-red-eye'
					size={20}
					themas{themas.color.gray}
				 />
			</View>

			<Text style={style.titleInput}>SENHA</Text>
			<TextInput 
				style={style.input}
				value={password}
				onChangeText={setPassword}
				/>
		  </View>
		  <View style={style.boxBotom}>
			<TouchableOpacity style={style.button} onpresss={()=>getLogin()}>
				<Text style={style.textButton}>Entrar</Text>
			</TouchableOpacity>

		  </View>
			<Text style={style.textBottom}>Não tem conta? <Text style={{color:themas.color.primary}}>Crie agora!</Text></Text>
		  <View>

		     


	)
}



STYLE

Styles

import  {StyleSheet} from "react-native";


export const style = StyleSheet.create({
	container:{
	flex:1,
	alignItens: 'center',
	justifyContent: 'center',
  },
	boxTop:{
	   height:Dimensions.get('window').height/3,
	   width: '100%',
	   //backgroundColor: 'red',
	   alignItens: 'center',
	   justifyContent: 'center'
  },
	boxMid:{
	   height:Dimensions.get('window').height/4,
	   width: '100%',
	   //backgroundColor: 'green'
	   paddingHorizontal:37
  },

	boxBotton:{
	   height:Dimensions.get('window').height/3,
	   width: '100%',
	   alignItens:'center',

  },
  logo:{
	width:80,
	height:80
  },
	text:{
	     fontWeight:'bold',
	     marginTop:40,
	     fontSize:18
     },

	titleInput:{
	     marginLeft:5,
	     color:themas.colocr.gray,
	     marginTop:20
     },

	BoxInput:{
	     width: '100%',
	     height:40,
	     borderWidth:1,
	     borderRadius:40,
	     marginTop:10,
	     flexDirection: 'row',
	     alignItens: 'center',
	     paddingHorizontal:5,
	     backgroundColor:themas.color.lightgray,
	     borderColor:themas.color.lightgray
     },

	input:{
	     height: '100%',
	     width:''90%',
	     borderRadius:40,
	     paddingLeft:5
     },

	button:{
	     widht:250,
	     height:50,
	     alignItens:'center',
	     justifyContente:'center',
	     backgroundColor:themas.color.primary,
	     borderRadius:40,
	     shadowColor:'#000',
	     shadowOffset: {
		width:0,
		height:3,
	     },
	     shadowOpacity: 0.29,
	     shadowrRadius: 4.65,
	     elevation: 7,
     },
	textButton:{}
	     fontSize:16,
	     color:'#FFFF',
	     fontWeight:'bold'
     },
	textBottom:{
	     fontSize:16,
	     color:themas.colors.gray
     }

})



App.tsx

App.tsx


import { StatusBar } from 'expo-status-bar';
import { StyleSheet, Text, View } from 'react-native';
import Login from './src/pages/login';

export default function App() {
	return (
	   <Login/>
   );

} 

const styles = StyleSheet.create({
 }
)




Png.d.ts

PNG.D.TS

declare module "*.png"



Themes.tsx


THEMES.TSX


export const themas = {
	colors:{
	    primary: '#878af6',
	    secondary: '#ffffff',
	    lightFray: '#d7d8d7',
	    gray: 'gary',
	    bgScreen: '#f1f7fa'


	}

}
