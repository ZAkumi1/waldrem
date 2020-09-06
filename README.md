def parsear_linea_log(logline):
match = re.match(PATRON_LOGS_APACHE, logline)
    if match is None:
 # Optionally, you can change this to just ignore if each line of data is not critical.
 # For this example, we want to ensure that the format is consistent.
raise Exception("Linea de log no valida: %s" % logline)
    return Row(
    ip = match.group(1),
    cliente = match.group(2),
    id_usuario = match.group(3),
    fecha_hora = match.group(4),
    metodo = match.group(5),
    url = match.group(6),
    protocolo = match.group(7),
    cod_respuesta = int(match.group(8)),
    tamano_contenido = long(match.group(9)),
    referer = match.group(10),
    agente = match.group(11)
)
