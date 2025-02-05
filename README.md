Audio Transcoding Project 🎵➡️🎶

This project performs audio transcoding, converting an input audio file from its original codec to the Opus codec, and packaging the encoded output into an MKV container.

**📌 Key Features:**

Decodes the source file’s audio codec

Resamples the audio if needed

Encodes the audio into Opus

Muxes the encoded audio into an MKV (.mkv) container


**🖥️ Command-Line Usage:**

AudioTranscoding.exe <input_file_name> <output_file_name>

Example:
AudioTranscoding.exe input.aac output.mkv

**🔄 Processing Flow:**

            +-----------------------+
            |  input_format_context |  (Reads AAC input)
            +-----------+-----------+
                        |
                        v
            +----------------------+
            |  input_codec_context |  (AAC Decoder)
            +-----------+----------+
                        |
                        v
            +---------------------+
            |   Decode Module     |  (Decodes AAC to raw PCM)
            +---------------------+
                        |
                        v
            +---------------------+
            |  Audio Resampling   |  (Convert PCM to match Opus specs)
            +---------------------+
                        |
                        v
            +----------------------+
            | output_codec_context |  (Opus Encoder)
            +----------------------+
                        |
                        v
            +----------------------+
            | Encode & Muxing      |  (Pack Opus into MKV)
            +----------------------+
                        |
                        v
            +----------------------+
            | output_format_context |  (Writes MKV file)
            +----------------------+
                        |
                        v
                      MKV (Opus)
