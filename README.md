# Proyect-report-
Gender Recognition
\documentclass[journal]{IEEEtran}
\IEEEoverridecommandlockouts
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%% PRINCIPALES PAQUETES %%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{fancyhdr}
\usepackage{graphicx}
\usepackage[spanish, es-tabla]{babel}
\usepackage[utf8]{inputenc}
\usepackage{color}
\usepackage{hyperref}
\usepackage{wrapfig}
\usepackage{array}
\usepackage{multirow}
\usepackage{adjustbox}
\usepackage{nccmath}
\usepackage{subfigure}
\usepackage{amsfonts,latexsym} % para tener disponibilidad de diversos simbolos
\usepackage{enumerate}
\usepackage{booktabs}
\usepackage{float}
\usepackage{threeparttable}
\usepackage{array,colortbl}
\usepackage{ifpdf}
\usepackage{rotating}
\usepackage{cite}
\usepackage{stfloats}
\usepackage{url}
\usepackage{listings}
\usepackage{amsmath}
\usepackage{makecell}%To keep spacing of text in tables
\setcellgapes{2pt}%parameter for the spacing in tables
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%% CREAR Y REESCRIBIR ALGUNOS COMANDOS %%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcolumntype{P}[1]{>{\centering\arraybackslash}p{#1}}  %% Se crea un nuevo tipo de columna llamada P.
\newcommand{\tabitem}{~~\llap{\textbullet}~~}
\newcommand{\ctt}{\centering\scriptsize\textbf} %%\ctt abrevia el comando \centering\scriptsize\textbf
\newcommand{\dtt}{\scriptsize\textbf} %%\dtt abrevia el comando \scriptsize\textbf
\renewcommand\IEEEkeywordsname{Palabras clave}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%


% correct bad hyphenation here
\hyphenation{op-tical net-works semi-conduc-tor} %% Con este comando se especifican como pueden seprarse las sílabas adecuadamente en caso una palabra quede en dos lineas diferentes de texto

\graphicspath{ {figs/} }  %%Ruta donde se encuentran las imágenes, que esté vacio indica que las imagenes están dentro de la misma carpeta que contiene el archivo .tex


%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%% ENCABEZADO DE LAS PÁGINAS TIPO UMNG %%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcommand{\MYhead}{\smash{\scriptsize
\hfil\parbox[t][\height][t]{\textwidth}{\centering
\begin{picture}(0,0) \put(-0,-17){\includegraphics[width=10mm]{Universidad Católica Boliviana _San Pablo_ UCB.jpg}} \end{picture} \hspace{6.4cm}
INFORME DE PROYECTO \hspace{5.15cm} Versión 1.0\\
\hspace{6.45cm} INGENIERÍA MECATRÓNICA \hspace{4.65cm} Semestre 2020-1\\
\underline{\hspace{ \textwidth}}}\hfil\hbox{}}}
\makeatletter
% normal pages
\def\ps@headings{%
\def\@oddhead{\MYhead}%
\def\@evenhead{\MYhead}}%
% title page
\def\ps@IEEEtitlepagestyle{%
\def\@oddhead{\MYhead}%
\def\@evenhead{\MYhead}}%
\makeatother
% make changes take effect
\pagestyle{headings}
% adjust as needed
\addtolength{\footskip}{0\baselineskip}
\addtolength{\textheight}{-1\baselineskip}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%% INICIO DEL DOCUMENTO %%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\begin{document}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%% TÍTULO DEL DOCUMENTO %%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\title{Detector de genero con Python}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%% AUTORES %%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%
\author{Aguilar~Brian,~
        Argote~Misael,~Molina~Mariana
        y~Ortega~Sinei\\
				Profesor:~Salazar~Edgar\\% stops a space
\thanks{El presente documento corresponde a un informe de práctica de la materia de ``Señales y Sistemas'' presentado en la Universidad Católica Boliviana San Pablo.}} %\thanks anexa una nota a pie de página donde se puede colocar alguna información sobre la naturaleza del documento.
%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Comando que indica la generación del título
\maketitle
%%%%%%%%%%%%%%%%%%%%%
%%%%%% RESUMEN %%%%%%
%%%%%%%%%%%%%%%%%%%%%
\begin{abstract}
Existe mucha información que puede ser extraída por medio de la voz, tal como la edad, las emociones, el lenguaje y el mismo género. En el presente proyecto se realizara un estudio del procesamiento de señales por medio del lenguaje de programación Python enfocado en la detección del genero de los hablantes. La principal característica para identificar la voz del usuario sera mediante a la frecuencia de su voz.

\end{abstract}
% En el resumen no se recomienda colocar citaciones bibliográficas.
%%%%%%%%%%%%%%%%%%%%%%
%%% PALABRAS CLAVE %%%
%%%%%%%%%%%%%%%%%%%%%%
\begin{IEEEkeywords}
Frecuencia, Genero, Procesamiento de señales, Python 

\end{IEEEkeywords}
%%%%%%%%%%%%%%%%%%%%%%
%\IEEEpeerreviewmaketitle
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%% PRIMERA SECCIÓN DEL DOCUMENTO %%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\section{Objetivos}
\IEEEPARstart{E}{l} objetivo de este proyecto es proporcionar un sistema que proporcione el reconocimiento de género por medio de la interacción entre el usuario y la computadora.

\subsection{Marco teórico}
\subsection{\textbf{Morfología de la voz humana}}
La voz se produce en la laringe y la glotis es el órgano de fonación humano. El proceso por el cual se emite la voz es por medio del aire que procede de los pulmones y es ayudado por el diafragma que ,sometido a presión, hace vibrar las cuerdas vocales. (Vozalia,2008)
\subsection{\textbf{Frecuencia de la voz humana}}
La frecuencia de la voz se mide hercios (Hz). Así, el rango de frecuencias de la voz humana está entre los 250 y 3.000 Hz. Es cierto que algunos fonemas están situados entre los 4.000 y los 8.000 Hz.

La frecuencia media de la voz masculina es de 106 Hz y con un rango de 77 Hz a 482 Hz. En cuanto a la voz femenina su frecuencia es de 193 Hz, con un rango de 137 Hz a 634 Hz. (EcuRed, 2010)

\subsection{\textbf{Procesamiento de señales}}

