# pytorch-a3c

다음은 비동기적 어드밴티지 액터 크리틱(A3C: Asynchronous Advantage Actor Critic)의 파이토치 버전입니다. 참고: ["Asynchronous Methods for Deep Reinforcement Learning"](https://arxiv.org/pdf/1602.01783v1.pdf).

이는 [Universe Starter Agent](https://github.com/openai/universe-starter-agent)에 영감을 받아 구현되었습니다.
Universe Starter Agent와는 다르게 논문에서 처럼 공유 통계치를 가진 옵티마이저를 사용합니다.

이 저장소를 인용하시려면 다음 bibtex 형식을 사용해주세요:

    @misc{pytorchaaac,
      author = {Kostrikov, Ilya},
      title = {PyTorch Implementations of Asynchronous Advantage Actor Critic},
      year = {2018},
      publisher = {GitHub},
      journal = {GitHub repository},
      howpublished = {\url{https://github.com/ikostrikov/pytorch-a3c}},
    }

## A2C

동기 버전 및 다른 알고리즘을 살펴보실 것을 **강력히 권장드립니다** : [pytorch-a2c-ppo-acktr](https://github.com/ikostrikov/pytorch-a2c-ppo-acktr).

제 경험상으로 A2C 이 A3C 보다 잘 작동하고, ACKTR 은 이 둘 보다 더 잘 작동합니다. 그리고 PPO는 연속 제어에 정말 적합한 알고리즘입니다. 먼저 A2C/PPO/ACKTR을 시도해보시고 필요에 따라서만 A3C 을 사용하실 것을 권장드립니다.
더 자세한 정보는 [OpenAI 블로그](https://blog.openai.com/baselines-acktr-a2c/) 에서 찾을 수 있습니다.

## 오픈소스 기여

오픈소스 기여를 환영합니다. 이 코드를 더 발전시킬 방법이 있다면 pull request를 주저하지 말고 날려주세요.

## 사용법
```bash
# 파이썬 3에서만 작동합니다.
python3 main.py --env-name "PongDeterministic-v4" --num-processes 16
```

이 코드는 16개의 프로세스 외에 별도의 스레드에서 평가를 실행합니다.

## 결과

16개의 프로세스로 PongDeterministic-v4 은 15분 안에 수렴합니다.
![PongDeterministic-v4](images/PongReward.png)

BreakoutDeterministic-v4 은 몇 시간 이상 걸립니다.
