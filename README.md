
# FLock.io

## Donanım
50 GB disk ve bununla uyumlu CPU ve RAM yeterli olacaktır.

## Kurulum
Burada validatör kurulumu anlatılmıştır, isteyenler ana dökümantasyondan training node da kurabilir.

### Adımlar
1. Aşağıdaki komut ile sisteminizi güncelleyin:
```bash
sudo apt update && sudo apt upgrade -y
```

2. Anaconda'yı indirin:
```bash
wget https://repo.anaconda.com/archive/Anaconda3-2024.06-1-Linux-x86_64.sh
```

3. Anaconda kurulumu için şu komutu çalıştırın (enter'a basarak ilerleyin ve sonunda "yes" diyerek onaylayın):
```bash
bash Anaconda3-2024.06-1-Linux-x86_64.sh
```

4. Bu aşama uzun sürebilir, o sırada keyifli bir aktivite yapabilirsiniz.

5. Anaconda'nın PATH değişkenine ekleyin:
```bash
export PATH="/root/anaconda3/bin:$PATH"
echo 'export PATH="/root/anaconda3/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

6. FLock-io validatör reposunu klonlayın:
```bash
git clone https://github.com/FLock-io/llm-loss-validator.git
```

7. Conda ortamını oluşturun:
```bash
conda create -n llm-loss-validator python=3.10
conda activate llm-loss-validator
```

8. Gerekli paketleri yüklemek için:
```bash
cd llm-loss-validator
pip install -r requirements.txt
```

### Validatörü Başlatma
1. Flock hesabı oluşturun ve API anahtarınızı alın (sağ üstte bulunur).

2. Bir görev seçin ve 30 token stake edin.

3. Task'lar bir numaraya sahiptir (örneğin 10, 11, 12).

4. Hugging Face hesabı oluşturun.

5. Token oluştururken, istediğiniz izin türünü seçin (yazma izni veya tam izinli).

6. Tırnak işaretleri içini doldurup işaretleri kaldırın.

### Son Adımlar
1. Yeni bir screen başlatın:
```bash
screen -S flock
```

2. Validatör dizinine gidin:
```bash
cd ~/llm-loss-validator/src
```

3. Aşağıdaki komut ile validatörü başlatın ve ödüllerinizi kazanın:
```bash
bash start.sh --hf_token <h*gin-face-keyiniz> --flock_api_key <Flock-api-key>  --task_id <numara> --validation_args_file validation_config_cpu.json.example --auto_clean_cache False
```

Kurulum bu kadar, eğer bir sorun yaşarsanız, chat üzerinden çözeriz. Görüşmek üzere <3
@ruesandora'dan alıntıdır
