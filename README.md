# BlackScholes








		double calibHWTheta_t1t2(
			double bootstrap_a_0_t1,
			const double a,
			const double sigma_t1_t2,
			const double bondPrice_0_t2,
			const double t1,
			const double t2,
			const double init
		) 
		{
			const double dt = t2 - t1;
			const double C_0_T = (1 - std::exp(-1 * a*t2)) / a;
			const double sigmaPart = 1. / 2 * std::pow(sigma_t1_t2, 2) / a / a;
			sigmaPart *= dt + 3. / 2 / a - 2. / 1 * std::exp(-a*dt) + 1. / 2 / a * std::exp(-2 * a*dt);
			const double RR = -std::log(bondPrice_0_t2) - init* C_0_T - bootstrap_a_t0_t1 + sigmaPart;
			const double denom = dt + (1 - std::exp(-1 * a*dt) ) / a;

			return RR*a / denom;
		}


		stepFunc getHWTheta() {
			stepFunc ret;

			double bootstrapA_0_t = 0;
			for (int i = 0; i < steptime.size(); ++i) {

				double simga = stepFunc.~~~~;
				double bond = Reader.~~~~;
				double itheta = calibHWTheta_t1t2(
					bootstrapA_0_t, 
					a,
					sigma,
					bond,
					i,
					i + 1,
					init);

				bootstrapA_0_t = -1 * bondPrice_0_t2 - 1 * initR * C_0_T;
				vec.push_back(itheta);
			}//i
			return ret;
		}//stepFunc getHWTheta()
